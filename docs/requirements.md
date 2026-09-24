# Requirements

## Functional requirements

### FR-01 — Create task
The user can create a new task.

A task contains:
- title
- optional description
- priority
- status
- optional due date

### FR-02 — View task list
The user can view all existing tasks.

### FR-03 — View task details
The user can view the details of a single task.

### FR-04 — Update task
The user can modify an existing task.

Editable fields:
- title
- description
- priority
- due date

### FR-05 — Delete task
The user can permanently delete a task.

### FR-06 — Change task status
The user can change the lifecycle state of a task according to the allowed business rules.

### FR-07 — Filter tasks
The user can filter tasks by:
- status
- priority
- due date

### FR-08 — Sort tasks
The user can sort tasks by:
- creation date
- due date
- priority

## Task lifecycle rules

- `createdAt` is automatically assigned when the task is created and cannot be modified.
- `updatedAt` is automatically updated when the task changes.
- `completedAt` is set when the task enters the `DONE` state.
- `completedAt` is cleared if the task leaves the `DONE` state.
- `dueAt` represents both date and time.

## Task status

### TODO
The task has been created but work has not started yet.

### IN_PROGRESS
The task is currently being worked on.

### DONE
The task has been completed.

### CANCELLED
The task will no longer be carried out, but is kept in the system.

## Task priority

### LOW
The task has no particular urgency and can be postponed.

### MEDIUM
The task has normal importance and should be addressed in the regular workflow.

### HIGH
The task requires attention before lower-priority tasks.

## Task state transitions

Task-it does not enforce a strict workflow between task states.

A task can transition from any state to any other different state.

Examples:

- `TODO -> IN_PROGRESS`
- `TODO -> DONE`
- `IN_PROGRESS -> TODO`
- `DONE -> IN_PROGRESS`
- `CANCELLED -> TODO`

When a task enters the `DONE` state:

- `completedAt` is automatically set to the current timestamp.

When a task leaves the `DONE` state:

- `completedAt` is cleared.

## Default values

- A newly created task always starts with status `TODO`.
- If no priority is explicitly provided, the task receives priority `LOW`.

## Cancellation vs deletion

Cancelling a task does not remove it from the system.

A `CANCELLED` task is preserved and can later transition to another valid state.

Deleting a task permanently removes it.

## Main business rules

### Title

- A task must have a title.
- The title cannot be blank.
- The title has a maximum length of 256 characters.
- Leading and trailing whitespace is removed.
- Consecutive whitespace is normalized.

### Description

- The description is optional.
- The description has a maximum length of 4096 characters.

### Due date

- `dueAt` is optional.
- When `dueAt` is assigned or changed, it must be later than the current time.
- A completed or cancelled task may retain an expired `dueAt` as historical information.
- When restoring a cancelled task whose `dueAt` has expired, the user must either provide a new valid `dueAt` or remove the due date.

### Priority

- Priority defaults to `LOW`.
- Priority can be changed at any time.

### Status

- A newly created task always starts as `TODO`.
- A task can transition from any status to any other different status.
- Setting the status to its current value is treated as a no-op.

### Completion

- When a task enters the `DONE` state, `completedAt` is set to the current timestamp.
- When a task leaves the `DONE` state, `completedAt` is cleared.

### Modification

- Tasks can be edited regardless of their current status.
- Any effective modification updates `updatedAt`.
- No-op operations do not update `updatedAt`.

### Deletion

- A task can be permanently deleted regardless of its current status.

### Temporal consistency

- `createdAt` is automatically assigned when the task is created.
- `createdAt` is immutable.
- `updatedAt` cannot precede `createdAt`.
- `completedAt`, when present, cannot precede `createdAt`.

### Duplicates

- Multiple tasks may have the same title.