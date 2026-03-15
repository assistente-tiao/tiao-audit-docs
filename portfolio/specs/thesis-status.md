# Thesis Status and Kill-Switch Workflow

## Goal
Define how thesis state is stored, reviewed, and surfaced without letting the agent overwrite manual governance controls.

## Storage Location
- Primary storage: `Teses e Status` tab in Google Sheets

## Core Fields
- ticker
- status_tese
- kill_switch
- ultima_revisao
- proximo_catalisador
- conviccao
- notas

## Status Semantics
- `🟢` = thesis intact / positive
- `🟡` = thesis under watch / mixed evidence
- `🔴` = thesis impaired / high caution

## Kill-Switch Rule
- Kill switch is manual input only in V1.
- Agent reads it, references it, and alerts on triggered conditions.
- Agent does not create, edit, or infer kill-switch thresholds automatically.

## Review Workflow
1. Operator or analysis flow updates thesis status manually or via explicit reviewed process.
2. Daily and weekly jobs read current values.
3. If a trigger condition or adverse result is detected, agent references the existing status and kill switch in reporting.
4. If kill switch is already marked as triggered, agent escalates in summary output.

## Alert Rules
- Mention thesis status in weekly briefing when relevant.
- Surface kill-switch-triggered names immediately in daily/special alerts.
- Never suppress a manual red or triggered state.

## Validation
- every portfolio ticker may have at most one thesis-status row
- manual kill-switch text is preserved verbatim
- agent outputs must distinguish status reading from independent opinion
