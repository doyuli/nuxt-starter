<script setup lang="ts">
import {
  ArrowRight,
  Boxes,
  CheckCircle2,
  Layers3,
  Moon,
  Sparkles,
  Terminal,
} from '@lucide/vue'
import { Button } from '@/components/ui/button'
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'

const highlights = [
  {
    icon: Boxes,
    title: 'Nuxt 4 foundation',
    description: 'A clean app structure with TypeScript, Vue 3, and pnpm-first scripts.',
  },
  {
    icon: Layers3,
    title: 'shadcn-ready UI',
    description: 'Button and Card primitives are wired with Tailwind tokens and class merging.',
  },
  {
    icon: CheckCircle2,
    title: 'Quality checks',
    description: 'ESLint, Vitest, type checks, lint-staged, and commit message hooks are ready.',
  },
]

const stack = ['Nuxt', 'Vue', 'Tailwind', 'shadcn-vue', 'VueUse', 'Vitest']
</script>

<template>
  <main class="min-h-svh overflow-hidden bg-background text-foreground">
    <section class="relative isolate px-6 py-8 sm:px-8 lg:px-12">
      <div class="pointer-events-none absolute inset-0 -z-10 bg-[linear-gradient(to_right,var(--border)_1px,transparent_1px),linear-gradient(to_bottom,var(--border)_1px,transparent_1px)] bg-size-[64px_64px] opacity-35" />
      <div class="pointer-events-none absolute inset-x-0 top-0 -z-10 h-64 bg-[radial-gradient(ellipse_at_top,var(--muted),transparent_68%)]" />

      <header class="mx-auto flex max-w-6xl items-center justify-between">
        <div class="flex items-center gap-2 text-sm font-medium">
          <span class="flex size-8 items-center justify-center rounded-md bg-primary text-primary-foreground">
            <Sparkles class="size-4" aria-hidden="true" />
          </span>
          Nuxt Starter
        </div>
        <Button variant="ghost" size="sm" as="a" href="https://nuxt.com/docs" target="_blank" rel="noreferrer">
          Docs
          <ArrowRight class="size-4" aria-hidden="true" />
        </Button>
      </header>

      <div class="mx-auto grid min-h-[calc(100svh-4rem)] max-w-6xl items-center gap-12 py-16 lg:grid-cols-[1.05fr_0.95fr] lg:py-20">
        <div class="max-w-2xl">
          <div class="mb-6 inline-flex items-center gap-2 rounded-full border bg-background px-3 py-1 text-sm text-muted-foreground shadow-sm">
            <Moon class="size-3.5" aria-hidden="true" />
            Tailwind tokens, dark mode, and shadcn primitives included
          </div>

          <h1 class="text-balance text-5xl font-semibold tracking-normal sm:text-6xl lg:text-7xl">
            Nuxt Starter
          </h1>

          <p class="mt-6 max-w-xl text-pretty text-lg leading-8 text-muted-foreground">
            Start with Nuxt 4, shadcn-vue, Tailwind CSS v4, and practical checks already in place.
          </p>

          <div class="mt-8 flex flex-col gap-3 sm:flex-row">
            <Button size="lg" as="a" href="https://nuxt.com/docs/getting-started/introduction" target="_blank" rel="noreferrer">
              Start building
              <ArrowRight class="size-4" aria-hidden="true" />
            </Button>
            <Button variant="outline" size="lg" as="a" href="https://www.shadcn-vue.com/docs/introduction" target="_blank" rel="noreferrer">
              shadcn-vue
            </Button>
          </div>

          <div class="mt-8 flex flex-wrap gap-2">
            <span
              v-for="item in stack"
              :key="item"
              class="rounded-full border bg-background px-3 py-1 text-sm text-muted-foreground"
            >
              {{ item }}
            </span>
          </div>
        </div>

        <div class="relative">
          <div class="absolute -inset-4 -z-10 rounded-4xl border bg-muted/40" />
          <div class="overflow-hidden rounded-xl border bg-card text-card-foreground shadow-2xl shadow-foreground/10">
            <div class="flex items-center justify-between border-b px-4 py-3">
              <div class="flex items-center gap-2">
                <span class="size-3 rounded-full bg-chart-1" />
                <span class="size-3 rounded-full bg-chart-4" />
                <span class="size-3 rounded-full bg-chart-2" />
              </div>
              <span class="text-xs text-muted-foreground">app/pages/index.vue</span>
            </div>

            <div class="space-y-5 p-5">
              <div class="rounded-lg bg-primary p-5 text-primary-foreground">
                <div class="mb-10 flex items-center justify-between">
                  <Terminal class="size-5" aria-hidden="true" />
                  <span class="rounded-full bg-primary-foreground/15 px-2.5 py-1 text-xs">ready</span>
                </div>
                <p class="text-2xl font-semibold leading-tight">
                  pnpm dev
                </p>
                <p class="mt-2 text-sm text-primary-foreground/75">
                  Local server on localhost:3000
                </p>
              </div>

              <div class="grid gap-3 sm:grid-cols-2">
                <div class="rounded-lg border p-4">
                  <p class="text-sm text-muted-foreground">
                    UI
                  </p>
                  <p class="mt-1 text-xl font-semibold">
                    shadcn
                  </p>
                </div>
                <div class="rounded-lg border p-4">
                  <p class="text-sm text-muted-foreground">
                    Tests
                  </p>
                  <p class="mt-1 text-xl font-semibold">
                    Vitest
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="mx-auto grid max-w-6xl gap-4 pb-10 md:grid-cols-3">
        <Card v-for="item in highlights" :key="item.title">
          <CardHeader>
            <div class="mb-3 flex size-10 items-center justify-center rounded-md bg-secondary text-secondary-foreground">
              <component :is="item.icon" class="size-5" aria-hidden="true" />
            </div>
            <CardTitle>{{ item.title }}</CardTitle>
            <CardDescription>{{ item.description }}</CardDescription>
          </CardHeader>
          <CardContent>
            <div class="h-1.5 rounded-full bg-secondary">
              <div class="h-full w-2/3 rounded-full bg-primary" />
            </div>
          </CardContent>
        </Card>
      </div>
    </section>
  </main>
</template>
