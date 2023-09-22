# Atividade N1 do PAC

📚 Avaliação N1 da disciplina de PAC do curso de Engenharia de Software da Universidade Católica de Santa Catarina.

# Tabela de Conteúdos
<!-- TOC -->
* [Atividade N1 do PAC](#atividade-n1-do-pac)
* [Tabela de Conteúdos](#tabela-de-conteúdos)
* [Equipe](#equipe)
* [Turma](#turma)
* [Telas do Design do Projeto](#telas-do-design-do-projeto)
  * [Mobile](#mobile)
  * [Web](#web)
* [Tarefas de Funcionalidades](#tarefas-de-funcionalidades)
* [Banco de Dados](#banco-de-dados)
<!-- TOC -->

# Equipe

| Integrantes                                  |
|----------------------------------------------|
| [Cristian Prochnow][github-cristian]         |
| [Gustavo Henrique Dias][github-gustavo]      |
| [Lucas Willian de Souza Serpa][github-lucas] |
| [Marlon de Souza][github-marlon]             |
| [Ryan Gabriel Mazzei Bromati][github-ryan]   |

# Turma

| 4ª fase de Engenharia de Software |
|-----------------------------------|
| Turma B                           |


# Telas do Design do Projeto

## Mobile

| ![mobile-001] | ![mobile-002] | ![mobile-003] | ![mobile-004] |
|---------------|---------------|---------------|---------------|
| ![mobile-005] | ![mobile-006] | ![mobile-007] | ![mobile-008] |
| ![mobile-009] | ![mobile-010] | ![mobile-011] |               |

## Web

| ![web-001] | ![web-002] | ![web-003] |
|------------|------------|------------|
| ![web-004] | ![web-005] | ![web-006] |
| ![web-007] | ![web-008] | ![web-009] |
| ![web-010] | ![web-011] |            |

# Tarefas de Funcionalidades

| Tarefas                                                 |
|---------------------------------------------------------|
| [Configurar o ambiente cloud no Firebase][task-001]     |
| [Criar o serviço de API com Supabase][task-002]         |
| [Desenvolvimento Inicial Mobile][task-003]              |
| [Desenvolvimento Inicial Web][task-004]                 |
| [Desenvolvimento Avançado Mobile][task-005]             |
| [Desenvolvimento Avançado Web][task-006]                |
| [Desenvolvimento Complementar Mobile][task-007]         |
| [Desenvolvimento Complementar Web][task-008]            |
| [Publicação do projeto web na Vercel][task-009]         |
| [Publicação do projeto mobile na Google Play][task-010] |

# Banco de Dados

```postgresql
create table
  public.task
(
  task_id            uuid                     not null default gen_random_uuid(),
  created_at         timestamp with time zone not null default now(),
  initial_coordinate character varying null,
  end_coordinate     character varying null,
  description        character varying null,
  observation        character varying null,
  initial_date       date null,
  end_date           date null,
  play_date          date null,
  constraint Task_pkey primary key (task_id)
) tablespace pg_default;

create table
  public.user
(
  user_id    uuid                     not null default gen_random_uuid(),
  created_at timestamp with time zone not null default now(),
  phone      character varying null,
  birthday   date null,
  name       character varying null,
  email      character varying null,
  admin      boolean null,
  constraint User_pkey primary key (user_id)
) tablespace pg_default;

create table
  public.user_task
(
  "user" uuid not null,
  task   uuid null,
  constraint user_task_task_fkey foreign key (task) references task (task_id),
  constraint user_task_user_fkey foreign key ("user") references "user" (user_id)
) tablespace pg_default;
```



[github-cristian]: https://github.com/cristianprochnow
[github-gustavo]: https://github.com/gustapine
[github-lucas]: https://github.com/Lucaswillians
[github-marlon]: https://github.com/Marlon-Souza16
[github-ryan]: https://github.com/urltapas

[mobile-001]: ./.github/telas/mobile/001.png
[mobile-002]: ./.github/telas/mobile/002.png
[mobile-003]: ./.github/telas/mobile/003.png
[mobile-004]: ./.github/telas/mobile/004.png
[mobile-005]: ./.github/telas/mobile/005.png
[mobile-006]: ./.github/telas/mobile/006.png
[mobile-007]: ./.github/telas/mobile/007.png
[mobile-008]: ./.github/telas/mobile/008.png
[mobile-009]: ./.github/telas/mobile/009.png
[mobile-010]: ./.github/telas/mobile/010.png
[mobile-011]: ./.github/telas/mobile/011.png

[web-001]: ./.github/telas/web/001.png
[web-002]: ./.github/telas/web/002.png
[web-003]: ./.github/telas/web/003.png
[web-004]: ./.github/telas/web/004.png
[web-005]: ./.github/telas/web/005.png
[web-006]: ./.github/telas/web/006.png
[web-007]: ./.github/telas/web/007.png
[web-008]: ./.github/telas/web/008.png
[web-009]: ./.github/telas/web/009.png
[web-010]: ./.github/telas/web/010.png
[web-011]: ./.github/telas/web/011.png

[task-001]: https://cristianprochnow.atlassian.net/browse/HIGIA-5?atlOrigin=eyJpIjoiNDhkYjMyZGY3OTczNDZiNDk0YjVkNzc5M2I0YmRjNjAiLCJwIjoiaiJ9
[task-002]: https://cristianprochnow.atlassian.net/browse/HIGIA-82?atlOrigin=eyJpIjoiNDdiMmFmMWI4OGI1NDQ3NzkxNjJiNzJjZTlhZjJjMGIiLCJwIjoiaiJ9
[task-003]: https://cristianprochnow.atlassian.net/browse/HIGIA-6?atlOrigin=eyJpIjoiYzc2NjI1ODdiMmU1NDM4ZmE5Y2Y4MTIzNzFmMmU3NzciLCJwIjoiaiJ9
[task-004]: https://cristianprochnow.atlassian.net/browse/HIGIA-13?atlOrigin=eyJpIjoiMGMzZGQyOGYwOWYxNDZiZDgzZmE2YWYxOTc1NDc4MGQiLCJwIjoiaiJ9
[task-005]: https://cristianprochnow.atlassian.net/browse/HIGIA-24?atlOrigin=eyJpIjoiNWZlMjgyZjJhNjgwNGE1MDk5YTAwZWE0YjU1MDdiODkiLCJwIjoiaiJ9
[task-006]: https://cristianprochnow.atlassian.net/browse/HIGIA-33?atlOrigin=eyJpIjoiZTg4M2QwNDI0YjBkNGQ5YmE1N2NjNmY1MzlmMDRlNWIiLCJwIjoiaiJ9
[task-007]: https://cristianprochnow.atlassian.net/browse/HIGIA-44?atlOrigin=eyJpIjoiYzQwNDY2OTc0OWFiNDEwYjkwY2E0N2UwZWRiYTViOGEiLCJwIjoiaiJ9
[task-008]: https://cristianprochnow.atlassian.net/browse/HIGIA-53?atlOrigin=eyJpIjoiYTIxNzI2MmVkNjZlNGY0Zjg1N2RkY2FkYWQwZTczYzQiLCJwIjoiaiJ9
[task-009]: https://cristianprochnow.atlassian.net/browse/HIGIA-62?atlOrigin=eyJpIjoiMDczOGRjYjA0NWEzNDRhY2FmZTY4ZWQ2NmFkYjkxODQiLCJwIjoiaiJ9
[task-010]: https://cristianprochnow.atlassian.net/browse/HIGIA-67?atlOrigin=eyJpIjoiZTA4NTgyM2M1NDZjNDhiMWI2ZTcxMzQwMDg5M2RkNDQiLCJwIjoiaiJ9