## OneToMany and ManyToOne

In NestJS, you can establish relationships between entities using the TypeORM library for database interaction. One-to-Many and Many-to-One relationships are common database relationship types, and you can define them using decorators and classes.

Here's how you can set up One-to-Many and Many-to-One relationships in NestJS using TypeORM:

### One-to-Many Relationship:
Assuming you have two entities, User and Post, where a single user can have multiple posts:

Define the User and Post entities:

user.entity.ts
```bash
import { Entity, PrimaryGeneratedColumn, Column, OneToMany } from 'typeorm';
import { Post } from './post.entity';

@Entity()
export class User {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  username: string;

  @OneToMany(() => Post, post => post.user)
  posts: Post[];
}
```

post.entity.ts

```bash
import { Entity, PrimaryGeneratedColumn, Column, ManyToOne } from 'typeorm';
import { User } from './user.entity';

@Entity()
export class Post {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  title: string;

  @ManyToOne(() => User, user => user.posts)
  user: User;
}
```

### Many-to-One Relationship:
Assuming you have two entities, Comment and Article, where multiple comments can belong to a single article:

Define the Comment and Article entities:

comment.entity.ts

```bash
import { Entity, PrimaryGeneratedColumn, Column, ManyToOne } from 'typeorm';
import { Article } from './article.entity';

@Entity()
export class Comment {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  text: string;

  @ManyToOne(() => Article, article => article.comments)
  article: Article;
}

```
article.entity.ts

```bash
import { Entity, PrimaryGeneratedColumn, Column, OneToMany } from 'typeorm';
import { Comment } from './comment.entity';

@Entity()
export class Article {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  title: string;

  @OneToMany(() => Comment, comment => comment.article)
  comments: Comment[];
}
```

## Sequelize in Nest JS

Sequelize is an Object-Relational Mapping (ORM) library for Node.js that provides a powerful way to interact with relational databases using JavaScript. It allows you to work with databases like PostgreSQL, MySQL, SQLite, and MSSQL in a more convenient and abstracted manner by representing database tables as JavaScript objects and enabling you to perform database operations using JavaScript code.
