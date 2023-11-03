Simple-Spring-Backend
This is a simple rest server 
Using: `Spring Boot`, `Spring Security`, `Spring Data JPA`.

Versions:
JDK 17.0.8
kotlin api version 1.8 (1.8.22)
Gradle 8.2.1


Table of users:
```sql
CREATE TABLE IF NOT EXISTS public.users
(
    id bigint PRIMARY KEY  NOT NULL DEFAULT nextval('users_seq'::regclass),
    username character varying(100) COLLATE pg_catalog."default" NOT null UNIQUE,
    password character varying(100) COLLATE pg_catalog."default" NOT NULL,
	roles character varying[] COLLATE pg_catalog."default" NOT NULL,
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.users
    OWNER to postgres;
```

Table of todo:
```sql
CREATE TABLE IF NOT EXISTS public.todos
(
    id integer PRIMARY KEY NOT NULL DEFAULT nextval('todos_seq'::regclass),
	userid bigint NOT NULL,
    username character varying(100),
    content character varying(1000) COLLATE pg_catalog."default",
    checked boolean
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.todos
    OWNER to postgres;
```