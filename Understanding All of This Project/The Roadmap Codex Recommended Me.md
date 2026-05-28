
**Best Starting Point**
Start with [prisma/schema.prisma](C:/Users/Navid/Desktop/XBooks/prisma/schema.prisma).

That file tells you the domain model: `Item`, `Customer`, `Vendor`, `AdminUser`. Everything else exists to create, read, validate, display, protect, or format those models. If you start with React first, you’ll understand screens but not the system. If you start with Express first, you’ll understand routes but not the business objects. The schema is the map.

**Roadmap**
1. [prisma/schema.prisma](C:/Users/Navid/Desktop/XBooks/prisma/schema.prisma)  
Understand the nouns of the app. Ask: what data exists, which fields are required, which fields are optional, what relationships exist?

2. [backend/src/server.ts](C:/Users/Navid/Desktop/XBooks/backend/src/server.ts)  
This is the backend entry point. Read it to understand process startup: environment loads, admin bootstrap runs, Express app starts listening.

3. [backend/src/app.ts](C:/Users/Navid/Desktop/XBooks/backend/src/app.ts)  
This is the backend architecture hub. It wires middleware, static frontend hosting, public routes, protected routes, and error handling.

4. [backend/src/config/env.ts](C:/Users/Navid/Desktop/XBooks/backend/src/config/env.ts) and [backend/src/lib/prisma.ts](C:/Users/Navid/Desktop/XBooks/backend/src/lib/prisma.ts)  
These explain how runtime configuration and database access enter the app.

5. [backend/src/services/admin-bootstrap.ts](C:/Users/Navid/Desktop/XBooks/backend/src/services/admin-bootstrap.ts), [backend/src/routes/auth.ts](C:/Users/Navid/Desktop/XBooks/backend/src/routes/auth.ts), [backend/src/middleware/auth.ts](C:/Users/Navid/Desktop/XBooks/backend/src/middleware/auth.ts)  
Read these together. This is the authentication story: initial admin, login, token creation, protected API access.

6. [backend/src/utils/validation.ts](C:/Users/Navid/Desktop/XBooks/backend/src/utils/validation.ts), [backend/src/utils/request.ts](C:/Users/Navid/Desktop/XBooks/backend/src/utils/request.ts), [backend/src/middleware/error-handler.ts](C:/Users/Navid/Desktop/XBooks/backend/src/middleware/error-handler.ts)  
This is where backend robustness lives: parsing, validation, controlled errors, Prisma error translation.

7. [backend/src/routes/items.ts](C:/Users/Navid/Desktop/XBooks/backend/src/routes/items.ts)  
This is the most important feature route right now. Read every line. It shows how UI form data becomes validated database writes.

8. [backend/src/routes/customers.ts](C:/Users/Navid/Desktop/XBooks/backend/src/routes/customers.ts), [backend/src/routes/vendors.ts](C:/Users/Navid/Desktop/XBooks/backend/src/routes/vendors.ts), [backend/src/routes/summary.ts](C:/Users/Navid/Desktop/XBooks/backend/src/routes/summary.ts)  
These are simpler siblings. Compare them to `items.ts` to see reusable route patterns.

9. [backend/src/presenters/item-presenter.ts](C:/Users/Navid/Desktop/XBooks/backend/src/presenters/item-presenter.ts) and [backend/src/presenters/contact-presenter.ts](C:/Users/Navid/Desktop/XBooks/backend/src/presenters/contact-presenter.ts)  
These explain the boundary between database objects and API response objects. This is a very important architecture habit.

10. [frontend/src/main.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/main.tsx)  
Frontend entry point. Small, but it tells you how React enters the page.

11. [frontend/src/App.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/App.tsx)  
This is the frontend architecture hub. It owns auth state, app data loading, routing, protected layout, and refresh behavior.

12. [frontend/src/api.ts](C:/Users/Navid/Desktop/XBooks/frontend/src/api.ts) and [frontend/src/types.ts](C:/Users/Navid/Desktop/XBooks/frontend/src/types.ts)  
Read these right after `App.tsx`. They explain how frontend talks to backend and what shapes the frontend expects.

13. [frontend/src/layout/Sidebar.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/layout/Sidebar.tsx)  
This teaches navigation, app layout, and route identity.

14. [frontend/src/pages/LoginPage.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/pages/LoginPage.tsx)  
Read with `auth.ts`. This connects user input to backend login.

15. [frontend/src/pages/ItemsPage.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/pages/ItemsPage.tsx)  
This is the main frontend feature file. Read it slowly. Connect every form field to `backend/src/routes/items.ts` and every displayed table cell to `Item` in `types.ts`.

16. [frontend/src/pages/ContactsPage.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/pages/ContactsPage.tsx)  
This is a reusable page pattern for both customers and vendors.

17. [frontend/src/pages/HomePage.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/pages/HomePage.tsx), [frontend/src/pages/ReportsPage.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/pages/ReportsPage.tsx), [frontend/src/components/Stats.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/components/Stats.tsx), [frontend/src/components/Field.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/components/Field.tsx), [frontend/src/components/PageTitle.tsx](C:/Users/Navid/Desktop/XBooks/frontend/src/components/PageTitle.tsx)  
These are smaller UI building blocks and less central pages.

18. [frontend/src/styles.css](C:/Users/Navid/Desktop/XBooks/frontend/src/styles.css)  
Read this last. CSS is important, but if you read it too early, it becomes visual noise. Once you know the component structure, the styles will make sense.

19. Config files: [package.json](C:/Users/Navid/Desktop/XBooks/package.json), [backend/package.json](C:/Users/Navid/Desktop/XBooks/backend/package.json), [frontend/package.json](C:/Users/Navid/Desktop/XBooks/frontend/package.json), [frontend/vite.config.ts](C:/Users/Navid/Desktop/XBooks/frontend/vite.config.ts), [backend/tsconfig.json](C:/Users/Navid/Desktop/XBooks/backend/tsconfig.json), [frontend/tsconfig.json](C:/Users/Navid/Desktop/XBooks/frontend/tsconfig.json)  
Read these after the app code. They explain how the project runs, builds, proxies API calls, and compiles TypeScript.

Skip `backend/generated/prisma/*` at first. That is generated code. Useful later, but terrible as a learning entry point.

The most effective study loop for you would be: pick one workflow, then trace it end to end. For example, “save an item”:

`ItemsPage.tsx` form submit → `api.ts` `createItem` → `app.ts` route mounting → `auth.ts` protection → `items.ts` validation/create → `schema.prisma` `Item` model → `item-presenter.ts` response → `App.tsx` `loadData` refresh → `ItemsPage.tsx` table render.

That one trace will teach you more architecture than reading ten tutorials.