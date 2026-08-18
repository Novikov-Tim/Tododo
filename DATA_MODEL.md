# DATA_MODEL.md

## User

Поля:

- id
- username
- email
- password_hash
- created_at

## Category

Поля:

- id
- user_id
- parent_id
- name
- color
- created_at

Правила:

- у каждого пользователя есть категория unsorted;
- если задача создается без категории, она попадает в unsorted;
- если категория удаляется, её задачи переносятся в unsorted.

## Task

Поля:

- id
- user_id
- category_id
- title
- description
- note
- link
- priority
- status
- start_time
- end_time
- reminder_at
- repeat_rule
- created_at
- updated_at

Правила:

- если start_time и end_time пустые, задача отображается только в ежедневнике;
- если start_time и end_time заполнены, задача отображается в таймлайне;
- задача всегда принадлежит категории;
- выполненная задача не удаляется, а получает статус done.
