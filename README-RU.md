[English](README-EN.md)

# insurance-crm
Проект представляет собой систему управления взаимоотношения с клиентами для страховых компаний.
Реализован на `Node.js` с использованием `Fastify`, `Prisma ORM`, `PostgreSQL`

## Запуск проекта с докером
Для того, чтобы начать работу с проектом, нужен docker с образами `node:latest`, `nginx:latest`, `postgresql:latest`.
Nginx выступает в роли обратного прокси сервера.

Чтобы клонировать репозиторий введите команду:
`git clone https://github.com/AlteiOS0/insurance-crm.git`

Для сборки контейнера нужно прописать команду `docker compose build`

Далее для запуска контейнеров `docker compose up`

## Запуск проекта без докера

Для работы с проектом напрямую без докера, а также работы с проектом

Необходимо ввести команду для установки зависимостей `npm install`

Для деплоя в бд и генерации PrismaClient `npm run prisma:init`

И наконец для запуска сервера `npm run dev`

## Структура проекта
```
insurance
│   .dockerignore
│   .env
│   .gitignore
│   .prod.env
│   .test.env
│   compose.yaml
│   dockerfile
│   jest.config.js
│   jest.setup.js
│   package-lock.json
│   package.json
│   tsconfig.json
│
├───assets
│   ├───fonts
│   │       OpenSans-Bold.ttf
│   │       OpenSans-Regular.ttf
│   │       OpenSans-SemiBold.ttf
│   │
│   └───policies
├───nginx
│       nginx.conf
│
├───prisma
│   │   schema.prisma
│   │   
│   └───migrations
│       │   migration_lock.toml
│       │
│       └───20250513185830_init
│               migration.sql
│
└───src
    │   app.ts
    │   index.ts
    │
    ├───controllers
    │       clientController.ts
    │       insuranceProductController.ts
    │       loginController.ts
    │       policyController.ts
    │
    ├───plugins
    │       clientPlugin.ts
    │       insuranceProductPlugin.ts
    │       loginPlugin.ts
    │       policyPlugin.ts
    │       prismaPlugin.ts
    │       sessionPlugin.ts
    │
    ├───prisma
    │       prismaClient.ts
    │
    ├───repositories
    │       clientRepository.ts
    │       employeeRepository.ts
    │       insuranceProductRepository.ts
    │       policyNumberReservedRepository.ts
    │       policyRepository.ts
    │       sessionRepository.ts
    │
    ├───routes
    │       clientRoutes.ts
    │       insuranceProductRoutes.ts
    │       loginRoutes.ts
    │       policyRoutes.ts
    │
    ├───schemas
    │   │   ajv.ts
    │   │   clientSchema.ts
    │   │   clientValidator.ts
    │   │   employeeSchema.ts
    │   │   employeeValidator.ts
    │   │   insuranceProductSchema.ts
    │   │   insuranceProductValidator.ts
    │   │   policySchema.ts
    │   │   policyValidator.ts
    │   │   sessionSchema.ts
    │   │   sessionValidator.ts
    │   │
    │   ├───share
    │   │       responseSchemas.ts
    │   │
    │   └───utils
    │           partialDeep.ts
    │           typingEnum.ts
    │
    ├───services
    │       clientService.ts
    │       insuranceProductService.ts
    │       loginService.ts
    │       policyService.ts
    │       sessionService.ts
    │       
    ├───tests
    │   ├───integration
    │   │   ├───client
    │   │   │       clientController.test.ts
    │   │   │       preparedData.ts
    │   │   │
    │   │   ├───insuranceProduct
    │   │   │       insuranceProductController.test.ts
    │   │   │       preparedData.ts
    │   │   │
    │   │   └───policy
    │   │       │   policyController.test.ts
    │   │       │
    │   │       └───assets
    │   └───unit
    │       │   prismaClient.ts
    │       │   singleton.ts
    │       │
    │       ├───client
    │       │       clientService.test.ts
    │       │       preparedClientData.ts
    │       │
    │       ├───policy
    │       │       policyService.test.ts
    │       │       preparedData.ts
    │       │
    │       ├───product
    │       │       insuranceProductService.test.ts
    │       │       preparedData.ts
    │       │
    │       └───utils
    │               ajvError.ts
    │
    └───types
            deepPartial.ts
            index.d.ts
            personalData.ts
```
