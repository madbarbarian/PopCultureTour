# Development Rules and Standards
# 開発ルールと標準

**Purpose**: Comprehensive development standards and coding guidelines for consistent, high-quality software development
**目的**: 一貫した高品質なソフトウェア開発のための包括的な開発標準とコーディングガイドライン

## 📋 Rule Categories / ルールカテゴリ

### **Global Development Rules / グローバル開発ルール**
| Rule Type / ルール種別 | File Location / ファイル場所 | Purpose / 目的 |
|---------|---------|---------|
| **Global Standards** | `.cursor/rules/globals.mdc` | Project-wide development process |
| **Technology Stack** | `.cursor/rules/techstack.mdc` | Technology choices and versions |
| **UI/UX Guidelines** | `.cursor/rules/uiux.mdc` | Design system and interface standards |
| **Task Management** | `.cursor/rules/todo.mdc` | Project task organization |
| **Database Design** | `.cursor/rules/db-blueprint.mdc` | Database schema and naming standards |
| **Next.js Standards** | `.cursor/rules/nextjs.mdc` | Next.js implementation patterns |
| **Authentication** | `.cursor/rules/clerk.mdc` | Clerk authentication implementation |

## 🌐 **Global Development Standards / グローバル開発標準**

### Core Development Process / コア開発プロセス
**Source**: `.cursor/rules/globals.mdc`
**Role / 役割**: Basic development process applied to the entire project / プロジェクト全体に適用される基本的な開発プロセス

#### **1. Analysis & Planning Phase / 分析・計画フェーズ**
- **Requirement Analysis**: Thorough requirement analysis before implementation / 実装前の徹底的な要件分析
- **Architecture Review**: Evaluate impact on existing system architecture
- **Resource Planning**: Estimate time, complexity, and resource requirements
- **Risk Assessment**: Identify potential risks and mitigation strategies

#### **2. Implementation Standards / 実装標準**
- **DRY Principle**: Check existing functionality before creating new implementations / 既存機能の確認（DRY原則）
- **Structure Adherence**: Maintain established directory structure and patterns / 確立されたディレクトリ構造の維持
- **Code Consistency**: Follow established coding conventions and styles / 一貫したコーディング標準
- **Documentation**: Document complex logic and architectural decisions

#### **3. Quality Management / 品質管理**
- **Task Verification**: Verify results of each development task / 各タスクの結果検証
- **Code Review**: Mandatory code review for all changes
- **Testing Requirements**: Comprehensive testing for new features
- **Performance Validation**: Ensure performance standards are met

#### **4. Security Standards / セキュリティ標準**
- **Input Validation**: All user inputs must be validated
- **Authentication**: Proper authentication and authorization
- **Data Protection**: Secure handling of sensitive data
- **Error Handling**: Secure error handling without information leakage

### Capabilities Enabled / 可能になること
- ✅ Systematic code quality assurance / 体系的なコード品質保証
- ✅ Efficient development process / 効率的な開発プロセス
- ✅ Consistent coding standards / 一貫したコーディング標準

## 🎯 **Cursor IDE Integration / Cursor IDE連携**

### Detailed Development Rules (.cursor/rules/) / 開発ルール詳細

#### **1. Technology Stack Definition / 技術スタック定義**
**File**: `.cursor/rules/techstack.mdc`
**Role / 役割**: Clarify project technology choices / プロジェクトの技術選択を明確化

**Frontend Technologies / フロントエンド技術**:
```yaml
Next.js: v14.2.25
  purpose: React framework with App Router
  usage: Primary frontend framework
  standards: Server Components first, ISR when needed

React: v18.2.0
  purpose: UI library
  usage: Component-based architecture
  standards: Functional components, hooks pattern

TypeScript: v5.2.2
  purpose: Typed JavaScript
  usage: All code files (.ts, .tsx)
  standards: Strict type checking, interface definitions
```

**UI Components / UIコンポーネント**:
```yaml
Shadcn/ui:
  purpose: Main UI component library
  usage: Primary component source
  standards: Prefer over custom components

Tailwind CSS: v3.4.1
  purpose: Utility-first CSS
  usage: All styling
  standards: Mobile-first responsive design

Radix UI:
  purpose: Accessible headless components
  usage: Complex interactive components
  standards: ARIA compliance required

Lucide React: v0.446.0
  purpose: Icon library
  usage: All icon implementations
  standards: Consistent icon sizing, semantic usage
```

**Authentication & Database / 認証・データベース**:
```yaml
Clerk: v6.12.9
  purpose: Authentication & user management
  usage: All authentication flows
  standards: Secure implementation, proper middleware

Prisma: v5.11.0
  purpose: TypeSafe ORM
  usage: All database operations
  standards: Schema-first approach, type safety

Database Evolution:
  current: Local SQLite
  planned: Supabase migration
  standards: Migration strategy documented
```

**Deployment / デプロイ**:
```yaml
Vercel:
  purpose: Recommended deployment platform
  usage: Production deployments
  standards: Environment-specific configurations
```

#### **2. UI/UX Design Rules / UI/UX設計ルール**
**File**: `.cursor/rules/uiux.mdc`
**Role / 役割**: Consistent user interface design / 一貫したユーザーインターフェース設計

**Core Principles / 主要原則**:
- **Shadcn/ui Priority**: Use Shadcn/ui components first / Shadcn/uiコンポーネントの優先使用
- **No Unauthorized Changes**: Existing UI cannot be modified without explicit approval / 既存UIの無許可変更禁止
- **Minimal Customization**: Keep customizations minimal and documented / 最小限のカスタマイズ

**Capabilities Enabled / 何ができるか**:
- ✅ Unified design system / 統一されたデザインシステム
- ✅ Accessibility compliance / アクセシビリティ確保
- ✅ Responsive design / レスポンシブデザイン

#### **3. Task Management Rules / タスク管理ルール**
**File**: `.cursor/rules/todo.mdc`
**Role / 役割**: Systematic project task management / プロジェクトタスクの体系的管理

**Task Status System / タスク管理方法**:
```markdown
- [ ] 未着手タスク (Pending tasks)
- [x] 完了タスク (Completed tasks)
- [~] 進行中タスク (In-progress tasks)
- [!] 問題ありタスク (Blocked/Issue tasks)
```

**Priority System / 優先度システム**:
```
🔴 緊急 (Critical - Immediate action required)
🟡 重要 (Important - High priority)
🟢 通常 (Normal - Standard priority)
⚪ 低優先 (Low - When time permits)
```

**Capabilities Enabled / 何ができるか**:
- ✅ Progress visualization / 進捗状況の可視化
- ✅ Dependency clarity / 依存関係の明確化
- ✅ Regular review cycles / 定期的なレビューサイクル

#### **4. Database Design Rules / データベース設計ルール**
**File**: `.cursor/rules/db-blueprint.mdc`
**Role / 役割**: Database design standardization / データベース設計の標準化

**Naming Conventions / 命名規則**:
```typescript
// Models: PascalCase
User, Project, TaskItem

// Fields: camelCase
firstName, lastName, createdAt, updatedAt

// Primary Key: Always 'id'
id: String @id @default(cuid())

// Foreign Keys: [tableName]Id
userId: String
projectId: String
```

**Capabilities Enabled / 何ができるか**:
- ✅ Consistent schema design / 一貫したスキーマ設計
- ✅ Prisma ORM optimization / Prisma ORM最適化
- ✅ Type safety assurance / 型安全性の確保

#### **5. Next.js Implementation Rules / Next.js実装ルール**
**File**: `.cursor/rules/nextjs.mdc`
**Role / 役割**: Next.js-specific implementation standards / Next.js固有の実装標準

**Recommended Directory Structure / 推奨ディレクトリ構造**:
```
src/
├── app/                    # App Router
│   ├── (marketing)/       # Marketing pages
│   ├── (dashboard)/       # Dashboard functionality
│   └── api/               # API routes
├── components/            # React components
│   ├── common/           # Shared components
│   └── ui/               # UI components
└── lib/                  # Utilities and helpers
```

**Capabilities Enabled / 何ができるか**:
- ✅ App Router utilization / App Router活用
- ✅ Server Components usage / Server Components使用
- ✅ ISR (Incremental Static Regeneration) implementation / ISR実装

#### **6. Clerk Authentication Implementation Rules / Clerk認証実装ルール**
**File**: `.cursor/rules/clerk.mdc`
**Role / 役割**: Standard Clerk authentication implementation / Clerk認証の標準実装

**Setup Process / 設定手順**:
1. **Environment Variables**: Configure `.env.local` / 環境変数設定
2. **Middleware Setup**: Configure `middleware.ts` / ミドルウェア設定
3. **Layout Configuration**: Setup `app/layout.tsx` / レイアウト設定
4. **Authentication Components**: Implement auth components / 認証コンポーネント使用

**Security Rules / セキュリティルール**:
- **Environment Management**: Proper environment variable handling / 環境変数の適切な管理
- **Protected Routes**: Explicit specification of auth-required routes / 認証必須ルートの明示的指定
- **Input Validation**: Validate all user inputs / ユーザー入力のバリデーション

**Capabilities Enabled / 何ができるか**:
- ✅ Secure authentication system / セキュアな認証システム
- ✅ User management functionality / ユーザー管理機能
- ✅ Server & client compatibility / サーバー・クライアント両対応

## 🛠️ **Technology Stack Standards / 技術スタック標準**

### Frontend Technologies / フロントエンド技術
**Source**: `.cursor/rules/techstack.mdc`

#### **Core Framework / コアフレームワーク**
```yaml
Next.js: v14.2.25
  purpose: React framework with App Router
  usage: Primary frontend framework
  standards: Server Components first, ISR when needed

React: v18.2.0
  purpose: UI library
  usage: Component development
  standards: Functional components, hooks pattern

TypeScript: v5.2.2
  purpose: Type-safe JavaScript
  usage: All code must be TypeScript
  standards: Strict mode, no any types
```

#### **UI Component System / UIコンポーネントシステム**
```yaml
Shadcn/ui:
  purpose: Main UI component library
  usage: Primary component source
  standards: Use existing components before custom

Tailwind CSS: v3.4.1
  purpose: Utility-first CSS framework
  usage: All styling through Tailwind
  standards: Design tokens, responsive design

Radix UI:
  purpose: Accessible headless components
  usage: Foundation for custom components
  standards: Accessibility first

Lucide React: v0.446.0
  purpose: Icon library
  usage: All icons through Lucide
  standards: Consistent icon sizing and styling
```

#### **Backend & Database / バックエンド・データベース**
```yaml
Prisma: v5.11.0
  purpose: TypeSafe ORM
  usage: All database operations
  standards: Schema-first, migration-driven

Clerk: v6.12.9
  purpose: Authentication & user management
  usage: All authentication features
  standards: Server-side validation, secure sessions

Supabase:
  purpose: PostgreSQL database platform
  usage: Production database (migration from SQLite)
  standards: RLS policies, secure API access
```

#### **Deployment / デプロイ**
```yaml
Vercel:
  purpose: Deployment platform
  usage: Recommended for Next.js applications
  standards: Environment-based configuration
```

## 🎨 **UI/UX Design Standards / UI/UXデザイン標準**

### Design System Principles / デザインシステム原則
**Source**: `.cursor/rules/uiux.mdc`

#### **Component Usage Hierarchy / コンポーネント使用階層**
1. **Shadcn/ui Components**: Use existing components first
2. **Radix UI Primitives**: For custom component foundation
3. **Custom Components**: Only when necessary, follow design tokens

#### **Design Constraints / デザイン制約**
- **No Unauthorized UI Changes**: Existing UI cannot be modified without approval
- **Minimal Customization**: Keep customizations to minimum necessary
- **Design Token Compliance**: Follow established design tokens
- **Accessibility First**: All components must meet WCAG AA standards

#### **Implementation Standards / 実装標準**
```typescript
// Component structure example
interface ComponentProps {
  variant?: 'default' | 'secondary' | 'destructive';
  size?: 'sm' | 'md' | 'lg';
  className?: string;
  children: React.ReactNode;
}

export function Component({
  variant = 'default',
  size = 'md',
  className,
  children,
  ...props
}: ComponentProps) {
  return (
    <div
      className={cn(
        componentVariants({ variant, size }),
        className
      )}
      {...props}
    >
      {children}
    </div>
  );
}
```

#### **Responsive Design Standards / レスポンシブデザイン標準**
```css
/* Breakpoint system */
sm: 640px   /* Mobile landscape */
md: 768px   /* Tablet */
lg: 1024px  /* Desktop */
xl: 1280px  /* Large desktop */
2xl: 1536px /* Extra large */
```

## 📋 **Task Management Standards / タスク管理標準**

### Task Organization System / タスク組織システム
**Source**: `.cursor/rules/todo.mdc`

#### **Task Status System / タスクステータスシステム**
```markdown
- [ ] 未着手タスク (Pending)
- [x] 完了タスク (Completed)
- [~] 進行中タスク (In Progress)
- [!] 問題ありタスク (Issue/Blocked)
```

#### **Priority System / 優先度システム**
```markdown
🔴 緊急 (Critical) - Immediate attention required
🟡 重要 (Important) - High priority, plan completion
🟢 通常 (Normal) - Standard priority
⚪ 低優先 (Low) - Nice to have, when time permits
```

#### **Task Documentation Standards / タスクドキュメント標準**
- **Clear Descriptions**: Each task must have clear, actionable description
- **Acceptance Criteria**: Define what constitutes task completion
- **Dependencies**: Document task dependencies and blocking issues
- **Estimates**: Provide time estimates for planning purposes

#### **Review Cycle / レビューサイクル**
- **Daily Standups**: Review progress and identify blockers
- **Weekly Planning**: Prioritize upcoming tasks
- **Sprint Reviews**: Evaluate completed work and lessons learned
- **Retrospectives**: Continuous improvement of processes

## 🗄️ **Database Design Standards / データベース設計標準**

### Naming Conventions / 命名規則
**Source**: `.cursor/rules/db-blueprint.mdc`

#### **Schema Naming / スキーマ命名**
```prisma
// Model names: PascalCase
model User {
  id        String   @id @default(cuid())
  email     String   @unique
  firstName String
  lastName  String
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt

  // Foreign keys: [ModelName]Id
  profileId String?
  profile   Profile? @relation(fields: [profileId], references: [id])
}

// Field names: camelCase
// Primary keys: id
// Foreign keys: [tableName]Id
// Timestamps: createdAt, updatedAt
```

#### **Database Standards / データベース標準**
- **Type Safety**: All database operations must be type-safe through Prisma
- **Migration Driven**: All schema changes through migrations
- **Indexing Strategy**: Proper indexing for performance
- **Data Validation**: Server-side validation for all data

#### **Prisma Best Practices / Prisma ベストプラクティス**
```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"  // Supabase PostgreSQL
  url      = env("DATABASE_URL")
}

// Use proper relations
model Post {
  id       String @id @default(cuid())
  title    String
  content  String
  authorId String
  author   User   @relation(fields: [authorId], references: [id])

  @@map("posts")  // Explicit table naming
}
```

## ⚡ **Next.js Implementation Standards / Next.js実装標準**

### Directory Structure / ディレクトリ構造
**Source**: `.cursor/rules/nextjs.mdc`

#### **App Router Structure / App Router構造**
```
src/
├── app/                    # App Router (Next.js 13+)
│   ├── (marketing)/       # Route groups for marketing pages
│   │   ├── page.tsx       # Landing page
│   │   ├── about/         # About page
│   │   └── pricing/       # Pricing page
│   ├── (dashboard)/       # Protected dashboard routes
│   │   ├── dashboard/     # Main dashboard
│   │   ├── settings/      # User settings
│   │   └── profile/       # User profile
│   ├── api/               # API routes
│   │   ├── auth/          # Authentication endpoints
│   │   ├── users/         # User management
│   │   └── webhooks/      # External webhooks
│   ├── globals.css        # Global styles
│   ├── layout.tsx         # Root layout
│   ├── loading.tsx        # Global loading UI
│   ├── error.tsx          # Global error UI
│   └── not-found.tsx      # 404 page
├── components/            # React components
│   ├── ui/               # UI components (Shadcn/ui)
│   ├── common/           # Shared components
│   ├── forms/            # Form components
│   └── layout/           # Layout components
├── lib/                  # Utility functions
│   ├── auth.ts           # Authentication utilities
│   ├── db.ts             # Database connection
│   ├── utils.ts          # General utilities
│   └── validations.ts    # Zod schemas
├── hooks/                # Custom React hooks
├── stores/               # State management (Zustand)
└── types/                # TypeScript type definitions
```

#### **Next.js Best Practices / Next.js ベストプラクティス**
```typescript
// Server Components by default
export default function Page() {
  return <div>Server Component</div>;
}

// Client Components when needed
'use client';
import { useState } from 'react';

export default function ClientPage() {
  const [state, setState] = useState('');
  return <div>Client Component</div>;
}

// API Routes with proper typing
import { NextRequest, NextResponse } from 'next/server';

export async function GET(request: NextRequest) {
  return NextResponse.json({ message: 'Success' });
}

// Metadata for SEO
export const metadata = {
  title: 'Page Title',
  description: 'Page description',
};
```

#### **Performance Standards / パフォーマンス標準**
- **Server Components First**: Use server components by default
- **ISR Implementation**: Use Incremental Static Regeneration when appropriate
- **Image Optimization**: Use Next.js Image component for all images
- **Bundle Analysis**: Regular bundle size monitoring
- **Core Web Vitals**: Meet Google Core Web Vitals standards

## 🔐 **Authentication Standards / 認証標準**

### Clerk Implementation Rules / Clerk実装ルール
**Source**: `.cursor/rules/clerk.mdc`

#### **Configuration Steps / 設定手順**
1. **Environment Variables**: Proper `.env` configuration
2. **Middleware Setup**: Configure `middleware.ts` for route protection
3. **Layout Configuration**: Set up `app/layout.tsx` with ClerkProvider
4. **Component Usage**: Use Clerk components for authentication flows

#### **Security Implementation / セキュリティ実装**
```typescript
// Middleware for route protection
import { authMiddleware } from "@clerk/nextjs";

export default authMiddleware({
  publicRoutes: ["/", "/about", "/pricing"],
  ignoredRoutes: ["/api/webhooks/(.*)"],
});

// Server-side authentication
import { auth } from "@clerk/nextjs";

export default async function ProtectedPage() {
  const { userId } = auth();

  if (!userId) {
    redirect('/sign-in');
  }

  return <div>Protected content</div>;
}

// Client-side authentication
import { useAuth } from "@clerk/nextjs";

export default function ClientComponent() {
  const { isSignedIn, user } = useAuth();

  if (!isSignedIn) {
    return <div>Please sign in</div>;
  }

  return <div>Welcome {user.firstName}</div>;
}
```

#### **Security Requirements / セキュリティ要件**
- **Environment Variable Security**: Proper management of sensitive keys
- **Route Protection**: Explicit protection for authenticated routes
- **Input Validation**: Server-side validation for all user inputs
- **Session Management**: Secure session handling
- **CSRF Protection**: Cross-site request forgery protection

## 🧪 **Testing Standards / テスト標準**

### Testing Strategy / テスト戦略

#### **Testing Pyramid / テストピラミッド**
```
End-to-End Tests (Playwright)
    ↑
Integration Tests (Jest + Testing Library)
    ↑
Unit Tests (Jest + Testing Library)
```

#### **Testing Requirements / テスト要件**
- **Unit Tests**: All utility functions and custom hooks
- **Integration Tests**: Component interactions and API routes
- **End-to-End Tests**: Critical user workflows
- **Accessibility Tests**: Automated accessibility testing

#### **Test File Organization / テストファイル組織**
```
__tests__/
├── components/           # Component tests
├── pages/               # Page tests
├── api/                 # API route tests
├── utils/               # Utility function tests
└── e2e/                 # End-to-end tests
```

## 📊 **Code Quality Standards / コード品質標準**

### Linting and Formatting / リンティングとフォーマット

#### **ESLint Configuration / ESLint設定**
```json
{
  "extends": [
    "next/core-web-vitals",
    "@typescript-eslint/recommended",
    "prettier"
  ],
  "rules": {
    "@typescript-eslint/no-unused-vars": "error",
    "@typescript-eslint/no-explicit-any": "error",
    "prefer-const": "error"
  }
}
```

#### **Prettier Configuration / Prettier設定**
```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2
}
```

#### **Husky Pre-commit Hooks / Huskyプリコミットフック**
```bash
#!/bin/sh
npm run lint
npm run type-check
npm run test
```

## 🔄 **CI/CD Standards / CI/CD標準**

### Deployment Pipeline / デプロイパイプライン

#### **GitHub Actions Workflow / GitHub Actionsワークフロー**
```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Run linting
        run: npm run lint

      - name: Run type checking
        run: npm run type-check

      - name: Run tests
        run: npm run test

      - name: Build application
        run: npm run build
```

#### **Quality Gates / 品質ゲート**
- **Code Coverage**: Minimum 80% test coverage
- **Type Safety**: No TypeScript errors
- **Linting**: No ESLint errors
- **Security**: No high-severity security vulnerabilities
- **Performance**: Lighthouse score > 90

## 🎯 **Performance Standards / パフォーマンス標準**

### Web Performance Metrics / Webパフォーマンス指標

#### **Core Web Vitals / コアウェブバイタル**
```
Largest Contentful Paint (LCP): < 2.5s
First Input Delay (FID): < 100ms
Cumulative Layout Shift (CLS): < 0.1
First Contentful Paint (FCP): < 1.8s
Time to Interactive (TTI): < 3.8s
```

#### **Bundle Size Optimization / バンドルサイズ最適化**
- **Tree Shaking**: Eliminate unused code
- **Code Splitting**: Route-based and component-based splitting
- **Dynamic Imports**: Lazy load non-critical components
- **Bundle Analysis**: Regular monitoring with `@next/bundle-analyzer`

#### **Image Optimization / 画像最適化**
```typescript
import Image from 'next/image';

// Optimized image usage
<Image
  src="/hero-image.jpg"
  alt="Hero image"
  width={800}
  height={600}
  priority // For above-the-fold images
  placeholder="blur"
  blurDataURL="data:image/jpeg;base64,..."
/>
```

## 📚 **Documentation Standards / ドキュメント標準**

### Code Documentation / コードドキュメント

#### **JSDoc Standards / JSDoc標準**
```typescript
/**
 * Calculates the total price including tax
 * @param price - The base price
 * @param taxRate - The tax rate as a decimal (e.g., 0.08 for 8%)
 * @returns The total price including tax
 * @example
 * calculateTotalPrice(100, 0.08) // Returns 108
 */
function calculateTotalPrice(price: number, taxRate: number): number {
  return price * (1 + taxRate);
}
```

#### **README Standards / README標準**
- **Clear Purpose**: What the component/module does
- **Usage Examples**: How to use the component/module
- **Props/Parameters**: Detailed parameter documentation
- **Dependencies**: Required dependencies and versions

---

**🎯 Development Philosophy / 開発哲学**: These rules ensure consistent, maintainable, and high-quality code while promoting developer productivity and collaboration.

**これらのルールは、開発者の生産性とコラボレーションを促進しながら、一貫性があり、保守可能で高品質なコードを保証します。**