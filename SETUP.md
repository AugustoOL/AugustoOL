# Como colocar isso no seu perfil do GitHub

Estes arquivos foram feitos para o seu **repositório especial de perfil**: o que
tem exatamente o mesmo nome do seu usuário (`github.com/AugustoOL/AugustoOL`).
É o README desse repositório que aparece na sua página de perfil.

## 1. Crie o repositório (se ainda não existir)

Vá em `github.com/new`, crie um repositório **público** chamado exatamente
`AugustoOL` (igual ao seu usuário). O GitHub vai avisar que é especial e vai
aparecer no seu perfil.

## 2. Suba estes arquivos para a raiz do repositório

- `README.md`
- `light.svg`
- `dark.svg`
- `generate.mjs`
- `package.json`
- `.github/workflows/jet-heatmap.yml` (mantenha essa pasta `.github/workflows`)

## 3. Ative permissão de escrita nas Actions

No repositório: `Settings` → `Actions` → `General` → `Workflow permissions`
→ marque **"Read and write permissions"** → Salvar.

Isso é necessário porque o workflow vai gerar o arquivo `dist/github-jet.svg`
sozinho, todo dia, e precisa poder commitar esse arquivo de volta no repo.

## 4. Rode o workflow uma vez, manualmente

Vá na aba `Actions` → clique em **"Update jet heatmap SVG"** → **"Run
workflow"**. Isso cria o arquivo `dist/github-jet.svg` pela primeira vez
(sem isso, a imagem do "jato" não aparece ainda).

## 5. Pronto

O README já referencia os arquivos certos (`light.svg`, `dark.svg`,
`dist/github-jet.svg`) usando o seu usuário `AugustoOL`. O workflow roda
sozinho todo dia às 05:30 UTC e re-desenha o heatmap com base nas suas
contribuições reais.

---

### Se quiser trocar algo depois

- **Textos do banner** (Subject, Role, Education, Contatos, stack): estão
  escritos à mão dentro de `light.svg` e `dark.svg`, dentro da área com os
  `<tspan class="key">...` e `<tspan class="value">...`. Pode editar
  diretamente lá.
- **A "arte ASCII" da foto** (lado esquerdo do banner): foi gerada a partir
  da sua foto. Se quiser trocar por outra foto, me manda a nova imagem que eu
  gero de novo.
- **Cores/velocidade do jato**: estão no topo do `generate.mjs`
  (`MAX_TARGETS`, `LOOP_DUR`, `FLASH_COLOR`, `BULLET_COLOR`, `BLAST_COLOR`).
