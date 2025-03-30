# Software Development RoadMap
Roadmap for software development.

## Mindset
> "Read requirements >> Think >> Analyze and make requirements clear >> Design system (DB/API/UI) >> Implement based on design >> Review and test >> Go live"

## Required Technical Skills
Make sure you understand all fundamentals and concepts below before starting with the projects:
- Database Design
    - [12 DB design principles](https://vertabelo.com/blog/database-design-principles/)
- API
    - [RESTful API Design](https://viblo.asia/p/restful-api-design-best-practices-LzD5dLVW5jY)
- Technical
    - ReactJS
        - Hooks (useEffect, useState, useRef, useMemo, useCallback, ...)
    - TypeScript
    - ORM
        - [TypeORM](https://typeorm.io/)
- Gitflow
    - https://viblo.asia/p/co-ban-ve-gitflow-workflow-4dbZNn6yZYM
- Clean Code:
    - [S.O.L.I.D principles](https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)
    - [Presentation and container components](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)

## Standard Working Flow

#### A. Make Requirements Clear
> Please carefully check and analyze all project requirements

- List down all important points:
    - How many features are needed?
        - Feature A:
        - Feature B:
    - Do we need to design a database for this project?
        - Use relational database (RDS) or non-relational DB (NoSQL) or both?

- Carefully review the design and requirements to ensure no points are missing

#### B. Design System
> Based on the design, let's start:

- Database Design
    - Design schemas (including primary keys, foreign keys, triggers if needed)

- API Design
    - Based on the database design above
    - List all APIs for each feature
        - Example feature A:
            - [GET] /api/v1/products: Get all active products
            - [POST] /api/v1/product: Create new product
            - [PUT] /api/v1/product: Update product
            - [DELETE] /api/v1/product: Delete product

- UI Design
    - Review UI design from the designer
    - If not available, we can design UI based on Figma or Adobe XD (not required for dev)

#### C. Work Based on Design

Each project will have the following main branches:
- Development: `dev`
- System Integration Testing: `sit`
- User Acceptance Testing: `uat`
- Staging (production-like environment): `staging`
- Production: `master` or `main`

#### Task Timeline

1. Build Skeleton Backend
    - Build initial source
    - Setup development pack: TypeScript, ESLint, Prettier, .gitignore, ...
    - Setup database connection and mapping
        - Define all entity schemas (based on database design)
> Ensure backend can connect to DB and is ready for implementing new features

2. Build Skeleton Frontend
    - Build initial source
    - Setup development pack: TypeScript, ESLint, Prettier, .gitignore, ...
    - Setup CSS/LESS/SASS if needed
    - Setup 3rd-party framework (Tailwind, Bootstrap, MUI, Ant Design, ...) if needed
> Ensure project has all dependencies set up without implementing features

3. Implement Feature
  
  > Example for ticket TDD-123: Manage Products 

- Jira:
    - Move ticket to In-Progress
  
- Backend:
    - Switch to dev branch: `git checkout dev`
    - Pull latest code: `git pull origin dev`
    - Checkout new feature branch from latest dev: `git checkout -b feature/tdd-123-add-products-feature`
    - Implement feature and APIs (add logic here)
    - Test done
    - Commit code to feature branch: `git add .` and `git commit -m "feat(products): add new feature" -m "ticket: TDD-123"`
    - Push code to remote branch: `git push origin feature/tdd-123-add-products-feature`
    - Create PR for review from `feature/tdd-123-add-products-feature` to `dev`
    - After leader review & merge -> deploy to server

- Frontend:
    - Switch to dev branch: `git checkout dev`
    - Pull latest code: `git pull origin dev`
    - Checkout new feature branch from latest dev: `git checkout -b feature/tdd-123-add-products-feature`
    - Add feature API calls from UI (fetch products, addProducts, removeProducts)
    - Implement UI ...
    - Test done
    - Commit code to feature branch: `git add .` and `git commit -m "feat(products): add new feature" -m "ticket: TDD-123"`
    - Push code to remote branch: `git push origin feature/tdd-123-add-products-feature`
    - Create PR for review from `feature/tdd-123-add-products-feature` to `dev`
    - After leader review & merge -> deploy to server

- Jira:
    - When `dev` is merged to `sit`, move ticket from `In-Progress` to `Ready For QA`

## Review Feature & Optimize

- Database
    - Add indexing for specific columns (please research indexing skills in DB)

- API
    - Optimize code with caching (Redis, memory cache)

- UI
    - Optimize rendering (prevent unnecessary renders)

## Utilities & Tools
- Source Control: [Git](https://git-scm.com/downloads)
- Database: [DBeaver](https://dbeaver.io/download/)
- Backend:
    - [ExpressJS](https://expressjs.com/)
    - [NestJS](https://docs.nestjs.com/)
- Frontend:
    - [ReactJS](https://react.dev/learn)
    - CSS:
        - [Tailwind](https://tailwindcss.com/)
        - [Bootstrap](https://getbootstrap.com/)
        - [Ant Design](https://ant.design/)
- Registry:
    - [Docker](https://www.docker.com/)
