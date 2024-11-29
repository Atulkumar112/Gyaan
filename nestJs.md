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
## Decorators in Sequelize
In Sequelize (which is used in NestJS for ORM-based database interactions), the four primary association decorators are:

1. @BelongsTo
2. @HasOne
3. @HasMany
4. @BelongsToMany

### 1. @BelongsTo (Many-to-One Relationship)
- Description: A many-to-one relationship where the current model contains a foreign key that points to another model. This is used when the current
model has multiple instances associated with a single instance of the other model.
- Typical Use Case: If a child model references a parent model with a foreign key.
- When to Use: Use @BelongsTo when the model has a foreign key to another model and you want to define that relationship. This is the most common use case for foreign keys in relational databases.


### 2. @HasOne (One-to-One Relationship)
- Description: A one-to-one relationship where the current model "has" one instance of another model. Typically, the associated model has a foreign key that references the current model.
- Typical Use Case: If a model has exactly one instance of another model, where the foreign key exists in the related model (the child model).
- Use @HasOne when a model has one and only one instance of another model, and the foreign key is located in the associated model. This is used to define one-to-one relationships.


### 3. @HasMany (One-to-Many Relationship)
- Description: A one-to-many relationship where the current model has many instances associated with one instance of another model. Typically, the related model will have a foreign key that points to the current model.
- Typical Use Case: Typical Use Case: If a parent model can have many child models, but each child model belongs to one parent.
- When to Use: Use @HasMany when the current model (the parent model) is the "one" in a one-to-many relationship and the associated model (the child model) has a foreign key pointing to the parent model. This is used when the parent model can have multiple child records.


### 4. @BelongsToMany (Many-to-Many Relationship)
- Description: A many-to-many relationship where two models are related through a join table. This is used when each model can have multiple related instances of the other model. The join table holds the foreign keys from both models.
- Typical Use Case: If both models can have many instances of the other model.
- When to Use: Use @BelongsToMany when you have a many-to-many relationship between models, and you want to define it using a join table.

## Sequelize in Nest JS

Sequelize is an Object-Relational Mapping (ORM) library for Node.js that provides a powerful way to interact with relational databases using JavaScript. It allows you to work with databases like PostgreSQL, MySQL, SQLite, and MSSQL in a more convenient and abstracted manner by representing database tables as JavaScript objects and enabling you to perform database operations using JavaScript code.
