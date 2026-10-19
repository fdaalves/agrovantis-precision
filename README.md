# Agrovantis Precision

Plataforma de agricultura de precisão para agrônomos e consultorias, com extensão para o produtor.

## Estado atual: Build 004

- Autenticação e dados em nuvem no Supabase.
- Consultorias, clientes, propriedades e talhões.
- Importação de limites KML e mapas com Leaflet.
- Campanhas de amostragem de solo, pontos e registro de coleta.
- Exportação de dados e CSV de amostragem.

Veja [docs/build004.md](docs/build004.md) para escopo e limitações. A homologação visual completa permanece pendente. Este repositório contém a versão recuperada do código salvo; não representa uma Build 005 concluída.

## Executar localmente

Requer Python 3:

```bash
python -m http.server 5173 --directory dist
```

Abra http://localhost:5173 no navegador. A aplicação depende de conexão com o Supabase e com os provedores de mapas.

## Configuração

A URL do projeto e a chave **publicável** estão em `dist/cloud.js`. Essa chave faz parte do cliente web; o acesso aos dados depende das políticas RLS do banco e da sessão do usuário. Nunca inclua senhas, tokens de sessão ou chaves administrativas (`service_role` / `sb_secret_`) no frontend.

As migrações do banco ainda não estão incluídas nesta exportação. Portanto, o código sozinho não provisiona um novo banco. O projeto Supabase existente é necessário para o funcionamento atual.

## Organização

- `dist/`: aplicação HTML, CSS e JavaScript, sem etapa de build.
- `dist/vendor/leaflet/`: biblioteca Leaflet e sua licença.
- `docs/`: documentação das entregas.
- `.openai/hosting.json`: configuração do Site original.

O envio ao GitHub não configura deploy automático nem altera a publicação existente.
