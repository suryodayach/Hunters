# BMAD-METHOD™ Guide for Existing Projects

## Overview

BMAD-METHOD™ is optimized to work with projects created using external tools like Android Studio, npm CLI, create-react-app, or Vite. This guide explains how to use BMAD for managing development workflows on existing projects.

## Key Concept: External Project Creation

Unlike traditional scaffolding tools, BMAD focuses on:

- **Analyzing** existing project structures
- **Planning** feature development with AI agents
- **Managing** sprints and tasks with Archon integration
- **Implementing** features following best practices

## Supported Project Types

### Android Projects

- Projects created in Android Studio
- Kotlin/Java applications
- Jetpack Compose or View-based UI
- Clean Architecture, MVVM, or MVI patterns

### Web Projects

- React apps (create-react-app, Vite)
- Vue.js applications
- Angular projects
- Next.js applications
- Remix apps
- Svelte/SvelteKit projects

## Workflow Overview

### 1. Project Analysis Phase

```bash
# After creating your project externally
cd your-project
npx bmad-method install

# Analyze existing project
npm run bmad:analyze
```

The Architect agent will:

- Scan project structure
- Identify technology stack
- Document architecture patterns
- Create analysis reports in `docs/analysis/`

### 2. Planning Phase

```bash
# Start planning workflow
npm run bmad:plan
```

Agents collaborate to create:

- **Project Brief** (Analyst)
- **Product Requirements** (PM)
- **Architecture Specifications** (Architect)
- **UI/UX Specifications** (UX Expert)

### 3. Sprint Management with Archon

BMAD integrates seamlessly with Archon MCP server for task management:

#### Sprint Setup

- 6-day sprint cycles
- Automatic task creation from stories
- 3-7 subtasks per story
- Kanban board with standard columns

#### Daily Workflow

1. **Sprint Planning**: SM agent creates sprint in Archon
2. **Story Creation**: Stories auto-generate Archon tasks
3. **Development**: Dev updates task status in Archon
4. **Testing**: QA creates bug tasks if needed
5. **Sprint Review**: PO validates completed work

### 4. Development Phase

```bash
# Generate story for implementation
npm run bmad:story

# Implement with dev agent
npm run bmad:dev
```

Story files contain:

- Complete implementation context
- Code snippets and patterns
- Test requirements
- Archon task ID for tracking

## Android-Specific Workflow

### Prerequisites

1. Create project in Android Studio
2. Set up module structure
3. Configure Gradle build
4. Initialize Git repository

### Using BMAD with Android

```bash
# Install BMAD in Android project
cd MyAndroidApp
npx bmad-method install

# Use Android-specific workflow
npm run bmad:workflow existing-android-app
```

### Android Templates Available

- `android-architecture-tmpl`: Clean Architecture documentation
- `android-compose-ui-tmpl`: Jetpack Compose UI specifications
- `android-story-tmpl`: Android-specific story format

### Android MCP Integration

BMAD uses Android MCP server for:

- Architecture pattern examples
- Material3 component references
- Use case implementations
- MVI/MVVM patterns

## Web Application Workflow

### Prerequisites

1. Create project with CLI tool:

   ```bash
   # React
   npx create-react-app my-app
   # or
   npm create vite@latest my-app -- --template react

   # Vue
   npm create vue@latest my-app

   # Angular
   ng new my-app

   # Next.js
   npx create-next-app@latest my-app
   ```

2. Install dependencies and verify build

### Using BMAD with Web Apps

```bash
# Install BMAD in web project
cd my-app
npx bmad-method install

# Use web-specific workflow
npm run bmad:workflow existing-web-app
```

### Web-Specific Considerations

- Framework detection (React, Vue, Angular, etc.)
- State management analysis
- Build tool configuration
- Testing setup recognition

## Archon Task Management

### Task Structure

```yaml
Epic (Major Feature)
└── Story (User Story)
└── Subtasks (3-7 implementation steps)
├── Domain implementation
├── Data layer
├── UI implementation
├── Testing
└── Documentation
```

### Archon Commands

Agents use Archon commands automatically:

- `create_project`: Initialize project board
- `create_task`: Story to task conversion
- `update_task`: Status updates during development
- `create_bug`: QA bug reporting
- `move_task`: Column transitions

### Sprint Workflow

1. **Day 1-2**: Planning and story creation
2. **Day 3-4**: Development and implementation
3. **Day 5**: Testing and bug fixes
4. **Day 6**: Review and deployment prep

## Templates for Existing Projects

### Analysis Templates

- `existing-project-analysis-tmpl`: Comprehensive project analysis
- `tech-stack-discovery-tmpl`: Technology stack documentation
- `brownfield-prd-tmpl`: PRD for existing projects

### Workflow Files

- `existing-android-app.yaml`: Android enhancement workflow
- `existing-web-app.yaml`: Web app enhancement workflow
- `archon-sprint-planning.yaml`: Sprint management with Archon

## Best Practices

### 1. Initial Setup

- Always run project analysis first
- Document existing patterns and conventions
- Identify technical debt early

### 2. Planning

- Create PRD even for small features
- Use sharding for large documents
- Link all artifacts to Archon tasks

### 3. Development

- Follow existing code conventions
- Use framework-specific patterns
- Update Archon status regularly

### 4. Testing

- Maintain existing test patterns
- Add tests for new features
- Track bugs in Archon

## Common Scenarios

### Adding a Feature to Existing Android App

```bash
# 1. Analyze current architecture
npm run bmad:analyze

# 2. Create feature PRD
npm run bmad:prd "Add user profile feature"

# 3. Generate architecture specs
npm run bmad:architect

# 4. Create story with Archon task
npm run bmad:story

# 5. Implement with tracking
npm run bmad:dev
```

### Enhancing React Application

```bash
# 1. Discover tech stack
npm run bmad:discover

# 2. Plan enhancement
npm run bmad:plan "Add real-time chat"

# 3. Sprint planning in Archon
npm run bmad:sprint

# 4. Develop with daily standups
npm run bmad:develop
```

## Troubleshooting

### Project Not Recognized

- Ensure package.json or build.gradle exists
- Run `bmad:analyze` to scan structure
- Check workflow prerequisites

### Archon Integration Issues

- Verify Archon MCP server is running
- Check mcp-config.yaml settings
- Ensure project exists in Archon

### Template Not Found

- Verify template exists in bmad-core/templates/
- Check template ID in workflow file
- Run `npm run validate` to check YAML

## Migration from Traditional BMAD

If you were using BMAD for project scaffolding:

1. **Old Way**: BMAD creates project structure
2. **New Way**: You create project, BMAD manages development

Benefits of the new approach:

- Use native tooling (Android Studio, npm)
- Better framework integration
- Standard project structures
- Easier onboarding for teams

## Next Steps

1. Review workflow files in `bmad-core/workflows/`
2. Explore templates in `bmad-core/templates/`
3. Configure Archon for your team
4. Start with project analysis
5. Plan your first sprint

## Support

For questions or issues:

- Check CLAUDE.md for AI assistance
- Review workflow YAML files
- Consult agent documentation
- Use Archon for task tracking
