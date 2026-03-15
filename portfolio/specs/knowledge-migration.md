# Knowledge Migration Plan

## Goal
Migrate portfolio analysis knowledge into `portfolio/knowledge/` as the analysis anchor for V1.

## Target Directory Layout
- `portfolio/knowledge/framework_analise.md`
- `portfolio/knowledge/portfolio_mapeamento.md`
- `portfolio/knowledge/deepdives/`
- `portfolio/knowledge/thematic/`
- `portfolio/knowledge/archive/`

## Expected Source Files
- framework_analise.md
- portfolio_mapeamento.md
- deepdive_*.md
- tese_suzb3_atualizada.md
- oil_analysis.md
- relatorio_macro_rotacao.md
- relatorio_safra_2025_26.md

## Naming Rules
- preserve canonical originals where possible
- move deep dives to `deepdives/{ticker}.md` when mapping is clear
- move thematic or macro docs to `thematic/`
- use `archive/` only for deprecated or duplicate material

## Migration Checklist
1. Collect source files
2. Deduplicate obvious copies/variants
3. Classify by type (framework, mapping, deepdive, thematic)
4. Copy into target directory
5. Verify readability and links/references
6. Record missing expected files

## Validation
- framework file exists
- at least one portfolio mapping file exists
- each migrated deep dive has clear ticker ownership
- missing files are explicitly logged, not ignored
