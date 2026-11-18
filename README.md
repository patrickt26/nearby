# Nearby

App mobile de cupons de desconto em estabelecimentos próximos. O usuário vê os locais no mapa, filtra por categoria, abre os detalhes de um local e resgata o cupom lendo um QR Code com a câmera.

Feito durante o NLW Pocket da Rocketseat (dezembro de 2024), com Expo e React Native.

## Funcionalidades

- Tela de boas-vindas com os passos de uso.
- Mapa com os estabelecimentos da categoria selecionada (React Native Maps) e marcador da posição do usuário.
- Filtro por categorias em lista horizontal.
- Lista de locais em *bottom sheet* arrastável sobre o mapa.
- Página do estabelecimento com capa, descrição, regras, contato e cupons disponíveis.
- Leitura de QR Code com a câmera (Expo Camera) e confirmação antes de resgatar o cupom.

## Stack

- Expo 52 e React Native 0.76 (nova arquitetura)
- Expo Router (rotas por arquivos, incluindo rota dinâmica `market/[id]`)
- React Native Maps, Expo Location e Expo Camera
- `@gorhom/bottom-sheet` e Reanimated
- Axios e TypeScript

## Como rodar

O app consome a API do evento (Node.js), que não está neste repositório. Com a API rodando na porta 3333:

1. Ajuste o `baseURL` em `src/services/api.ts` para o IP da sua máquina na rede local.
2. Instale e inicie:

```bash
npm install
npx expo start
```

3. Abra no Expo Go (Android ou iOS) ou em um emulador.

> A posição do usuário está fixa em São Paulo, perto dos locais cadastrados no banco de exemplo da API.

## Estrutura

```
src
├── app/                # rotas: boas-vindas, home (mapa) e market/[id]
├── components/         # categorias, lugares, cupom, botão, etc.
├── services/api.ts     # cliente HTTP
├── styles/             # cores, fontes e tema
└── utils/              # ícones das categorias
```
