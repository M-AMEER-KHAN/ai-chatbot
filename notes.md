# package.json
This `package.json` file is used in a Node.js project to manage project dependencies, scripts, and configurations. Here's a breakdown of its components:

### Private
```json
"private": true,
```
- The `private` field set to `true` indicates that this package is private and should not be published to a public registry like npm.

### Scripts
```json
"scripts": {
  "dev": "next dev --turbo",
  "build": "next build",
  "start": "next start",
  "lint": "next lint",
  "lint:fix": "next lint --fix",
  "preview": "next build && next start",
  "seed": "node -r dotenv/config ./scripts/seed.mjs",
  "type-check": "tsc --noEmit",
  "format:write": "prettier --write \"{app,lib,components}/**/*.{ts,tsx,mdx}\" --cache",
  "format:check": "prettier --check \"{app,lib,components}/**/*.{ts,tsx,mdx}\" --cache"
}
```
- `dev`: Runs the Next.js development server with the Turbo mode enabled.
- `build`: Builds the Next.js application for production.
- `start`: Starts the Next.js application in production mode.
- `lint`: Runs ESLint to check for code issues.
- `lint:fix`: Runs ESLint and fixes issues where possible.
- `preview`: Builds the application and then starts it (useful for previewing a production build locally).
- `seed`: Runs a script to seed the database, with environment variables loaded from a `.env` file.
- `type-check`: Runs TypeScript to check for type errors without emitting output.
- `format:write`: Formats the specified files using Prettier and caches the results.
- `format:check`: Checks the specified files for formatting issues using Prettier and caches the results.

### Dependencies
```json
"dependencies": {
  "@ai-sdk/openai": "^0.0.34",
  "@radix-ui/react-alert-dialog": "^1.1.1",
  "@radix-ui/react-dialog": "^1.1.1",
  "@radix-ui/react-dropdown-menu": "^2.1.1",
  "@radix-ui/react-icons": "^1.3.0",
  "@radix-ui/react-label": "^2.1.0",
  "@radix-ui/react-select": "^2.1.1",
  "@radix-ui/react-separator": "^1.1.0",
  "@radix-ui/react-slot": "^1.1.0",
  "@radix-ui/react-switch": "^1.1.0",
  "@radix-ui/react-tooltip": "^1.1.2",
  "@vercel/analytics": "^1.3.1",
  "@vercel/kv": "^2.0.0",
  "@vercel/og": "^0.6.2",
  "ai": "^3.2.16",
  "class-variance-authority": "^0.7.0",
  "clsx": "^2.1.1",
  "d3-scale": "^4.0.2",
  "date-fns": "^3.6.0",
  "focus-trap-react": "^10.2.3",
  "framer-motion": "^11.2.12",
  "geist": "^1.3.0",
  "nanoid": "^5.0.7",
  "next": "14.2.4",
  "next-auth": "5.0.0-beta.4",
  "next-themes": "^0.3.0",
  "openai": "^4.52.2",
  "react": "^18.3.1",
  "react-dom": "^18.3.1",
  "react-intersection-observer": "^9.10.3",
  "react-markdown": "^8.0.7",
  "react-syntax-highlighter": "^15.5.0",
  "react-textarea-autosize": "^8.5.3",
  "remark-gfm": "^3.0.1",
  "remark-math": "^5.1.1",
  "sonner": "^1.5.0",
  "usehooks-ts": "^3.1.0",
  "zod": "^3.23.8"
}
```
These are the runtime dependencies needed for the project. They include various packages for UI components, analytics, database handling, AI SDKs, state management, formatting, utility functions, and more. For example:
- `@radix-ui/*`: Various Radix UI components for building accessible React components.
- `next`: The Next.js framework for server-side rendering and static site generation.
- `react` and `react-dom`: React library and its DOM-specific bindings.
- `zod`: A TypeScript-first schema declaration and validation library.

### DevDependencies
```json
"devDependencies": {
  "@tailwindcss/typography": "^0.5.13",
  "@types/d3-scale": "^4.0.8",
  "@types/node": "^20.14.9",
  "@types/react": "^18.3.3",
  "@types/react-dom": "^18.3.0",
  "@types/react-syntax-highlighter": "^15.5.13",
  "@typescript-eslint/parser": "^7.14.1",
  "autoprefixer": "^10.4.19",
  "dotenv": "^16.4.5",
  "eslint": "^8.56.0",
  "eslint-config-next": "14.1.0",
  "eslint-config-prettier": "^9.1.0",
  "eslint-plugin-tailwindcss": "^3.14.0",
  "postcss": "^8.4.39",
  "prettier": "^3.3.2",
  "tailwind-merge": "^2.3.0",
  "tailwindcss": "^3.4.4",
  "tailwindcss-animate": "^1.0.7",
  "typescript": "^5.5.2"
}
```
These are the development dependencies, which include tools and libraries used during development, such as:
- `@types/*`: TypeScript type definitions for various libraries.
- `eslint` and related packages: For linting JavaScript and TypeScript code.
- `prettier`: Code formatting tool.
- `tailwindcss` and related packages: Utility-first CSS framework for styling.
- `typescript`: TypeScript language support.

### Package Manager
```json
"packageManager": "pnpm@8.6.3"
```
- Specifies that the project uses `pnpm` as its package manager, with version `8.6.3`.

This configuration ensures that the project is set up with all the necessary dependencies, scripts, and tools for development, building, and running a Next.js application.
# tailwind.config
This is a Tailwind CSS configuration file written in JavaScript. It customizes the Tailwind CSS framework to suit the specific needs of a project. Here's a breakdown of its components:

### Type Annotation
```javascript
/** @type {import('tailwindcss').Config} */
```
- This line provides TypeScript type information for the Tailwind CSS configuration object, which helps with IntelliSense and type checking.

### Module Exports
```javascript
module.exports = {
  darkMode: ['class'],
  content: [
    './pages/**/*.{ts,tsx}',
    './components/**/*.{ts,tsx}',
    './app/**/*.{ts,tsx}',
    './src/**/*.{ts,tsx}'
  ],
  prefix: '',
  theme: {
    container: {
      center: true,
      padding: '2rem',
      screens: {
        '2xl': '1400px'
      }
    },
    extend: {
      fontFamily: {
        sans: ['var(--font-geist-sans)'],
        mono: ['var(--font-geist-mono)']
      },
      colors: {
        border: 'hsl(var(--border))',
        input: 'hsl(var(--input))',
        ring: 'hsl(var(--ring))',
        background: 'hsl(var(--background))',
        foreground: 'hsl(var(--foreground))',
        primary: {
          DEFAULT: 'hsl(var(--primary))',
          foreground: 'hsl(var(--primary-foreground))'
        },
        secondary: {
          DEFAULT: 'hsl(var(--secondary))',
          foreground: 'hsl(var(--secondary-foreground))'
        },
        destructive: {
          DEFAULT: 'hsl(var(--destructive))',
          foreground: 'hsl(var(--destructive-foreground))'
        },
        muted: {
          DEFAULT: 'hsl(var(--muted))',
          foreground: 'hsl(var(--muted-foreground))'
        },
        accent: {
          DEFAULT: 'hsl(var(--accent))',
          foreground: 'hsl(var(--accent-foreground))'
        },
        popover: {
          DEFAULT: 'hsl(var(--popover))',
          foreground: 'hsl(var(--popover-foreground))'
        },
        card: {
          DEFAULT: 'hsl(var(--card))',
          foreground: 'hsl(var(--card-foreground))'
        }
      },
      borderRadius: {
        lg: 'var(--radius)',
        md: 'calc(var(--radius) - 2px)',
        sm: 'calc(var(--radius) - 4px)'
      },
      keyframes: {
        'accordion-down': {
          from: { height: '0' },
          to: { height: 'var(--radix-accordion-content-height)' }
        },
        'accordion-up': {
          from: { height: 'var(--radix-accordion-content-height)' },
          to: { height: '0' }
        }
      },
      animation: {
        'accordion-down': 'accordion-down 0.2s ease-out',
        'accordion-up': 'accordion-up 0.2s ease-out'
      }
    }
  },
  plugins: [require('tailwindcss-animate'), require('@tailwindcss/typography')]
}
```

### Configuration Details

#### Dark Mode
```javascript
darkMode: ['class'],
```
- Enables dark mode support by adding a class (`dark`) to the root element.

#### Content
```javascript
content: [
  './pages/**/*.{ts,tsx}',
  './components/**/*.{ts,tsx}',
  './app/**/*.{ts,tsx}',
  './src/**/*.{ts,tsx}'
],
```
- Specifies the paths to all files that should be scanned for class names. This helps Tailwind purge unused styles in production.

#### Prefix
```javascript
prefix: '',
```
- No prefix is added to the generated utility classes.

#### Theme
```javascript
theme: {
  container: {
    center: true,
    padding: '2rem',
    screens: {
      '2xl': '1400px'
    }
  },
  extend: {
    fontFamily: {
      sans: ['var(--font-geist-sans)'],
      mono: ['var(--font-geist-mono)']
    },
    colors: {
      border: 'hsl(var(--border))',
      input: 'hsl(var(--input))',
      ring: 'hsl(var(--ring))',
      background: 'hsl(var(--background))',
      foreground: 'hsl(var(--foreground))',
      primary: {
        DEFAULT: 'hsl(var(--primary))',
        foreground: 'hsl(var(--primary-foreground))'
      },
      secondary: {
        DEFAULT: 'hsl(var(--secondary))',
        foreground: 'hsl(var(--secondary-foreground))'
      },
      destructive: {
        DEFAULT: 'hsl(var(--destructive))',
        foreground: 'hsl(var(--destructive-foreground))'
      },
      muted: {
        DEFAULT: 'hsl(var(--muted))',
        foreground: 'hsl(var(--muted-foreground))'
      },
      accent: {
        DEFAULT: 'hsl(var(--accent))',
        foreground: 'hsl(var(--accent-foreground))'
      },
      popover: {
        DEFAULT: 'hsl(var(--popover))',
        foreground: 'hsl(var(--popover-foreground))'
      },
      card: {
        DEFAULT: 'hsl(var(--card))',
        foreground: 'hsl(var(--card-foreground))'
      }
    },
    borderRadius: {
      lg: 'var(--radius)',
      md: 'calc(var(--radius) - 2px)',
      sm: 'calc(var(--radius) - 4px)'
    },
    keyframes: {
      'accordion-down': {
        from: { height: '0' },
        to: { height: 'var(--radix-accordion-content-height)' }
      },
      'accordion-up': {
        from: { height: 'var(--radix-accordion-content-height)' },
        to: { height: '0' }
      }
    },
    animation: {
      'accordion-down': 'accordion-down 0.2s ease-out',
      'accordion-up': 'accordion-up 0.2s ease-out'
    }
  }
}
```
- Customizes the default theme. It includes container settings, extends the theme with custom fonts, colors, border radii, keyframes, and animations.
- `container`: Centers the container and adds padding.
- `fontFamily`: Defines custom sans and mono fonts.
- `colors`: Defines a variety of custom colors using CSS variables.
- `borderRadius`: Defines custom border radius values.
- `keyframes` and `animation`: Defines custom keyframe animations for accordion components.

#### Plugins
```javascript
plugins: [require('tailwindcss-animate'), require('@tailwindcss/typography')]
```
- Adds additional functionality to Tailwind CSS using plugins.
- `tailwindcss-animate`: Adds animation utilities.
- `@tailwindcss/typography`: Adds typography utilities.

This configuration tailors Tailwind CSS to fit the specific design and functionality requirements of the project, incorporating custom styles, animations, and component-specific configurations.

# prettier.config.js
This `prettier.config.js` file is used to configure Prettier, a code formatter, to enforce a consistent style across the project's codebase. Here's a detailed explanation of its settings:

### Type Annotation
```javascript
/** @type {import('prettier').Config} */
```
- This line provides TypeScript type information for the Prettier configuration object, which helps with IntelliSense and type checking.

### Configuration Options
```javascript
module.exports = {
  endOfLine: 'lf',
  semi: false,
  useTabs: false,
  singleQuote: true,
  arrowParens: 'avoid',
  tabWidth: 2,
  trailingComma: 'none',
  importOrder: [
    '^(react/(.*)$)|^(react$)',
    '^(next/(.*)$)|^(next$)',
    '<THIRD_PARTY_MODULES>',
    '',
    '^types$',
    '^@/types/(.*)$',
    '^@/config/(.*)$',
    '^@/lib/(.*)$',
    '^@/hooks/(.*)$',
    '^@/components/ui/(.*)$',
    '^@/components/(.*)$',
    '^@/registry/(.*)$',
    '^@/styles/(.*)$',
    '^@/app/(.*)$',
    '',
    '^[./]'
  ],
  importOrderSeparation: false,
  importOrderSortSpecifiers: true,
  importOrderBuiltinModulesToTop: true,
  importOrderParserPlugins: ['typescript', 'jsx', 'decorators-legacy'],
  importOrderMergeDuplicateImports: true,
  importOrderCombineTypeAndValueImports: true
}
```

#### Code Formatting Rules
- **`endOfLine: 'lf'`**
  - Ensures line endings are `LF` (line feed) instead of `CRLF` (carriage return line feed), which is common in Unix-based systems.

- **`semi: false`**
  - Omits semicolons at the ends of statements.

- **`useTabs: false`**
  - Uses spaces instead of tabs for indentation.

- **`singleQuote: true`**
  - Uses single quotes (`'`) instead of double quotes (`"`) for strings.

- **`arrowParens: 'avoid'`**
  - Omits parentheses around a sole arrow function parameter (e.g., `x => x` instead of `(x) => x`).

- **`tabWidth: 2`**
  - Sets the number of spaces per indentation level to 2.

- **`trailingComma: 'none'`**
  - Omits trailing commas in object and array literals, function parameters, etc.

#### Import Order Rules
- **`importOrder`**
  - Specifies the order in which imports should be organized. The order is as follows:
    - `react` and related imports.
    - `next` and related imports.
    - Third-party modules.
    - Empty line (for separation).
    - Type definitions.
    - Various internal module imports, such as types, config, lib, hooks, UI components, registry, styles, and app-related modules.
    - Empty line (for separation).
    - Relative imports (starting with `.` or `..`).

- **`importOrderSeparation: false`**
  - Disables additional empty lines between import groups.

- **`importOrderSortSpecifiers: true`**
  - Sorts the import specifiers within each import statement alphabetically.

- **`importOrderBuiltinModulesToTop: true`**
  - Ensures built-in modules are placed at the top of the import order.

- **`importOrderParserPlugins: ['typescript', 'jsx', 'decorators-legacy']`**
  - Specifies parser plugins to support TypeScript, JSX, and legacy decorators in the import order.

- **`importOrderMergeDuplicateImports: true`**
  - Merges duplicate import statements into a single import statement.

- **`importOrderCombineTypeAndValueImports: true`**
  - Combines type and value imports into a single import statement.

This configuration enforces a clean, consistent code style and import order throughout the project, enhancing readability and maintainability.

# postcss.config.js
This `postcss.config.js` file configures PostCSS, a tool for transforming CSS with JavaScript plugins. The file specifies which plugins PostCSS should use during the build process. Here's a breakdown of its components:

### Plugins Configuration
```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

### Explanation

#### `plugins`
- This object contains the plugins that PostCSS will use. Each key is the name of a plugin, and the value is its configuration.

#### `tailwindcss`
- This plugin enables Tailwind CSS, a utility-first CSS framework. The empty object `{}` indicates that the default configuration for Tailwind CSS should be used. Tailwind CSS will process the CSS files according to the rules defined in your Tailwind configuration file (`tailwind.config.js`).

#### `autoprefixer`
- This plugin automatically adds vendor prefixes to CSS rules, ensuring compatibility with different browsers. The empty object `{}` indicates that the default configuration for Autoprefixer should be used.

### Summary
- **`tailwindcss`**: Integrates Tailwind CSS into your project, allowing you to use its utility classes for styling.
- **`autoprefixer`**: Adds necessary vendor prefixes to your CSS rules for better cross-browser compatibility.

By using these plugins, your project can leverage the power of Tailwind CSS for rapid and consistent styling while ensuring that the CSS is compatible with a wide range of browsers thanks to Autoprefixer.

# middleware.ts
This `middleware.ts` file configures and exports middleware for a Next.js application, leveraging NextAuth.js for authentication and specifying a matcher to determine which routes the middleware should apply to. Here’s a detailed explanation of each part:

### Import Statements
```typescript
import NextAuth from 'next-auth'
import { authConfig } from './auth.config'
```
- **`NextAuth`**: Imports the primary NextAuth function from the `next-auth` package. This function is used to handle authentication.
- **`authConfig`**: Imports the authentication configuration from a local file (`auth.config`). This configuration includes settings such as providers, callbacks, session management, etc.

### NextAuth Configuration
```typescript
export default NextAuth(authConfig).auth
```
- **`NextAuth(authConfig)`**: Initializes NextAuth with the provided configuration object (`authConfig`). This setup includes all necessary authentication settings and providers.
- **`.auth`**: Exports the authentication handler which is responsible for handling authentication-related requests. This is a Next.js API route handler.

### Middleware Configuration
```typescript
export const config = {
  matcher: ['/((?!api|_next/static|_next/image|.*\\.png$).*)']
}
```
- **`config`**: Exports a configuration object for the middleware.
- **`matcher`**: Specifies a pattern to determine which routes the middleware should apply to. The pattern is a regular expression that includes:

#### Matcher Explanation
```typescript
matcher: ['/((?!api|_next/static|_next/image|.*\\.png$).*)']
```
- **`/((?!api|_next/static|_next/image|.*\\.png$).*)`**: This regular expression excludes specific paths and file types from middleware application. Here's the breakdown:
  - **`api`**: Excludes any route that starts with `/api`.
  - **`_next/static`**: Excludes any route that starts with `/_next/static`.
  - **`_next/image`**: Excludes any route that starts with `/_next/image`.
  - **`.*\\.png$`**: Excludes any route that ends with `.png`.

This pattern ensures that the middleware is applied to all routes except those matching the specified exclusions.

### Summary
1. **Imports**: `NextAuth` from `next-auth` and `authConfig` from a local configuration file.
2. **NextAuth Initialization**: Configures NextAuth with the provided settings and exports the authentication handler.
3. **Middleware Matcher**: Defines a regular expression to exclude specific paths and file types from the middleware, applying it only to relevant routes.

### Practical Use
- **Authentication Middleware**: This setup is primarily used to apply authentication middleware to all appropriate routes in the Next.js application.
- **Exclusions**: The matcher ensures that static assets, images, and API routes are not processed by the authentication middleware, which is efficient and necessary to avoid unnecessary authentication checks on non-page routes.

By configuring the middleware in this way, the application ensures that users are authenticated on all relevant pages while optimizing performance by excluding unnecessary routes.

# components.json
This `components.json` file is a configuration file that likely pertains to setting up a UI component library or design system for a project. Here’s a detailed explanation of each part:

### Schema
```json
"$schema": "https://ui.shadcn.com/schema.json"
```
- **`$schema`**: This specifies the JSON schema URL that validates the configuration file. The schema defines the structure and validation rules for the configuration, ensuring it follows the correct format.

### Style
```json
"style": "new-york"
```
- **`style`**: This sets the design style to "new-york". This is probably a predefined theme or design language that the component library will use. 

### React Server Components (RSC)
```json
"rsc": true
```
- **`rsc`**: Indicates that React Server Components are enabled. Setting this to `true` means that the project supports and utilizes React Server Components, which can help in optimizing the performance of React applications by allowing certain components to be rendered on the server.

### TypeScript with JSX (TSX)
```json
"tsx": true
```
- **`tsx`**: Indicates that the project uses TypeScript with JSX syntax. This enables TypeScript support for writing components with JSX, providing type-checking and other TypeScript features.

### Tailwind CSS Configuration
```json
"tailwind": {
  "config": "tailwind.config.ts",
  "css": "app/globals.css",
  "baseColor": "zinc",
  "cssVariables": true,
  "prefix": ""
}
```
- **`config`**: Specifies the path to the Tailwind CSS configuration file (`tailwind.config.ts`). This file contains the configuration for Tailwind CSS, such as theme customizations, plugins, and other settings.
- **`css`**: Specifies the path to the main CSS file where Tailwind CSS styles are applied (`app/globals.css`). This file is typically used to import Tailwind's base styles and any global custom styles.
- **`baseColor`**: Sets the base color for the design system to "zinc". This is likely used for the primary color palette in the project.
- **`cssVariables`**: When set to `true`, this enables the use of CSS variables for theme customization in Tailwind CSS. This allows for more dynamic and flexible styling.
- **`prefix`**: An empty string indicates that no prefix will be added to Tailwind CSS utility classes. If a prefix were provided, it would be prepended to all utility classes to avoid naming conflicts.

### Aliases
```json
"aliases": {
  "components": "@/components",
  "utils": "@/lib/utils"
}
```
- **`aliases`**: This section defines path aliases to simplify imports in the project.
  - **`components`**: Maps the alias `components` to the path `@/components`. This means that any import starting with `components` will be resolved to the `@/components` directory.
  - **`utils`**: Maps the alias `utils` to the path `@/lib/utils`. This simplifies importing utility functions or modules from the `@/lib/utils` directory.

### Summary
This `components.json` configuration file is designed to set up a UI component library or design system with the following features:
- Validated by a schema to ensure correct structure.
- Uses a predefined design style ("new-york").
- Supports React Server Components and TypeScript with JSX.
- Configures Tailwind CSS with a specific configuration file, base color, and support for CSS variables.
- Defines path aliases for easier imports of components and utilities.

By configuring these settings, the project can maintain a consistent design language, optimize performance, and simplify development with streamlined imports and TypeScript support.

# auth.ts
This `auth.ts` file configures authentication for a Next.js application using NextAuth.js with custom credential-based authentication. Here’s a detailed explanation of each part of the file:

### Import Statements
```typescript
import NextAuth from 'next-auth'
import Credentials from 'next-auth/providers/credentials'
import { authConfig } from './auth.config'
import { z } from 'zod'
import { getStringFromBuffer } from './lib/utils'
import { getUser } from './app/login/actions'
```
- **`NextAuth`**: The main NextAuth function for setting up authentication.
- **`Credentials`**: The credentials provider for custom username/password authentication.
- **`authConfig`**: A configuration object imported from a local file that contains NextAuth settings.
- **`z`**: The Zod library for schema validation.
- **`getStringFromBuffer`**: A utility function to convert an ArrayBuffer to a string.
- **`getUser`**: A function to fetch user data from the database or another data source.

### NextAuth Configuration
```typescript
export const { auth, signIn, signOut } = NextAuth({
  ...authConfig,
  providers: [
    Credentials({
      async authorize(credentials) {
        const parsedCredentials = z
          .object({
            email: z.string().email(),
            password: z.string().min(6)
          })
          .safeParse(credentials)

        if (parsedCredentials.success) {
          const { email, password } = parsedCredentials.data
          const user = await getUser(email)

          if (!user) return null

          const encoder = new TextEncoder()
          const saltedPassword = encoder.encode(password + user.salt)
          const hashedPasswordBuffer = await crypto.subtle.digest(
            'SHA-256',
            saltedPassword
          )
          const hashedPassword = getStringFromBuffer(hashedPasswordBuffer)

          if (hashedPassword === user.password) {
            return user
          } else {
            return null
          }
        }

        return null
      }
    })
  ]
})
```
### Explanation
#### Exported Authentication Methods
```typescript
export const { auth, signIn, signOut } = NextAuth({
```
- **`auth`**: The main authentication handler.
- **`signIn`**: A method to sign in a user.
- **`signOut`**: A method to sign out a user.

#### Configuration Spread
```typescript
...authConfig,
```
- Spreads the properties from `authConfig` into the NextAuth configuration object. This allows the configuration to be extended with additional settings.

#### Providers
```typescript
providers: [
  Credentials({
    async authorize(credentials) {
      // ...
    }
  })
]
```
- **`providers`**: Specifies the authentication providers. In this case, a custom credentials provider is used.

#### Authorize Function
```typescript
async authorize(credentials) {
  const parsedCredentials = z
    .object({
      email: z.string().email(),
      password: z.string().min(6)
    })
    .safeParse(credentials)

  if (parsedCredentials.success) {
    const { email, password } = parsedCredentials.data
    const user = await getUser(email)

    if (!user) return null

    const encoder = new TextEncoder()
    const saltedPassword = encoder.encode(password + user.salt)
    const hashedPasswordBuffer = await crypto.subtle.digest(
      'SHA-256',
      saltedPassword
    )
    const hashedPassword = getStringFromBuffer(hashedPasswordBuffer)

    if (hashedPassword === user.password) {
      return user
    } else {
      return null
    }
  }

  return null
}
```
- **`authorize`**: A function to authorize the user based on provided credentials.
  - **`parsedCredentials`**: Uses Zod to validate and parse the credentials object, ensuring the `email` and `password` fields are correct.
  - **`getUser`**: Fetches the user data by email.
  - **Password Hashing**:
    - **`TextEncoder`**: Encodes the password with the user-specific salt.
    - **`crypto.subtle.digest`**: Hashes the salted password using SHA-256.
    - **`getStringFromBuffer`**: Converts the hashed password buffer to a string.
  - **Password Comparison**: Compares the hashed password with the stored hashed password.
  - **Return Values**: Returns the user if the password matches; otherwise, returns `null`.

### Summary
This `auth.ts` file sets up NextAuth.js for handling custom credential-based authentication in a Next.js application. It includes:
- Importing necessary modules and configurations.
- Setting up NextAuth with custom credential provider.
- Validating and parsing credentials using Zod.
- Fetching user data and validating the password with hashing.
- Returning the authenticated user or `null` if authentication fails.

This approach ensures secure and validated user authentication with custom logic for password handling and validation.

# auth.config.ts
This `auth.config.ts` file defines the configuration for NextAuth.js, a library used for authentication in Next.js applications. The configuration includes settings for secret management, custom pages, and various callbacks that handle authorization, JSON Web Tokens (JWT), and session management. Here's a detailed explanation of each part:

### Import Statements
```typescript
import type { NextAuthConfig } from 'next-auth'
```
- **`NextAuthConfig`**: Imports the type for the NextAuth configuration, ensuring the configuration object adheres to the correct type structure.

### Exporting the Configuration
```typescript
export const authConfig = {
  secret: process.env.AUTH_SECRET,
  pages: {
    signIn: '/login',
    newUser: '/signup'
  },
  callbacks: {
    async authorized({ auth, request: { nextUrl } }) {
      const isLoggedIn = !!auth?.user
      const isOnLoginPage = nextUrl.pathname.startsWith('/login')
      const isOnSignupPage = nextUrl.pathname.startsWith('/signup')

      if (isLoggedIn) {
        if (isOnLoginPage || isOnSignupPage) {
          return Response.redirect(new URL('/', nextUrl))
        }
      }

      return true
    },
    async jwt({ token, user }) {
      if (user) {
        token = { ...token, id: user.id }
      }

      return token
    },
    async session({ session, token }) {
      if (token) {
        const { id } = token as { id: string }
        const { user } = session

        session = { ...session, user: { ...user, id } }
      }

      return session
    }
  },
  providers: []
} satisfies NextAuthConfig
```
### Configuration Details

#### Secret
```typescript
secret: process.env.AUTH_SECRET,
```
- **`secret`**: This is the secret used to encrypt session tokens. It is stored in an environment variable `AUTH_SECRET` to keep it secure.

#### Custom Pages
```typescript
pages: {
  signIn: '/login',
  newUser: '/signup'
}
```
- **`pages`**: Custom paths for sign-in and new user pages.
  - **`signIn`**: Redirects to `/login` for the sign-in page.
  - **`newUser`**: Redirects to `/signup` for the new user registration page.

#### Callbacks
Callbacks are functions that run at specific points in the authentication flow.

##### Authorized Callback
```typescript
async authorized({ auth, request: { nextUrl } }) {
  const isLoggedIn = !!auth?.user
  const isOnLoginPage = nextUrl.pathname.startsWith('/login')
  const isOnSignupPage = nextUrl.pathname.startsWith('/signup')

  if (isLoggedIn) {
    if (isOnLoginPage || isOnSignupPage) {
      return Response.redirect(new URL('/', nextUrl))
    }
  }

  return true
}
```
- **`authorized`**: Checks if the user is authorized to access the requested page.
  - **`isLoggedIn`**: Checks if the user is logged in.
  - **`isOnLoginPage`**: Checks if the user is on the login page.
  - **`isOnSignupPage`**: Checks if the user is on the signup page.
  - Redirects logged-in users away from the login or signup pages to the home page (`/`).
  - Returns `true` to allow access if the user is authorized.

##### JWT Callback
```typescript
async jwt({ token, user }) {
  if (user) {
    token = { ...token, id: user.id }
  }

  return token
}
```
- **`jwt`**: Customizes the JWT used for authentication.
  - If a user is present, the user's ID is added to the token.

##### Session Callback
```typescript
async session({ session, token }) {
  if (token) {
    const { id } = token as { id: string }
    const { user } = session

    session = { ...session, user: { ...user, id } }
  }

  return session
}
```
- **`session`**: Customizes the session object returned to the client.
  - If a token is present, it extracts the user ID from the token and adds it to the session user object.

#### Providers
```typescript
providers: []
```
- **`providers`**: An array where authentication providers (e.g., Google, GitHub) would be added. In this configuration, it is currently empty, meaning only custom credential-based authentication is set up elsewhere in the code.

#### Type Checking
```typescript
} satisfies NextAuthConfig
```
- **`satisfies NextAuthConfig`**: Ensures the configuration object adheres to the `NextAuthConfig` type, providing type safety and IntelliSense support.

### Summary
This `auth.config.ts` file configures NextAuth.js with:
- A secret for encrypting session tokens.
- Custom paths for sign-in and new user registration.
- Callbacks for authorization, JWT customization, and session management.
- An empty array for providers, indicating no third-party providers are configured yet.

These settings ensure secure and flexible authentication handling, redirecting users appropriately and customizing JWT and session data for the application.
