# Framework — Consistência Macro

## Objetivo
Garantir que recomendações micro sejam coerentes com o cenário-base do portfólio e com os fatores agregados de risco.

## Testes obrigatórios
### 1. Teste de coerência com cenário-base
A recomendação melhora ou piora a exposição do portfólio ao cenário-base?

### 2. Teste de cenário contrário
Se o cenário-base falhar, a posição funciona como hedge, amplificador de perda ou risco redundante?

### 3. Teste de fator
A posição adiciona exposição nova ou repete risco já dominante?

### 4. Teste de funding
Se houver redução em uma posição, para onde o capital vai? A realocação melhora ou piora a concentração?

### 5. Teste de honestidade
A recomendação está sendo guiada por valuation/tese ou por narrativa macro conveniente?

## Output mínimo
Toda conclusão relevante deve dizer explicitamente:
- qual cenário favorece a posição
- qual cenário a prejudica
- se a posição atua como core, amplificador, hedge ou erro de sobreposição
- o efeito provável sobre concentração de fator
