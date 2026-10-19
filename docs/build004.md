# Build 004 — Amostragem de solo

Campanhas por talhão com data planejada, profundidade inicial/final em centímetros e observações. Pontos com código único por campanha, coordenadas WGS84 em graus decimais, estado planejado/coletado e data da coleta. Exportação CSV com delimitador ponto e vírgula.

As tabelas `sampling_campaigns` e `sampling_points` usam RLS e vínculos compostos para impedir referências entre consultorias. Proprietário, administrador, agrônomo e técnico podem registrar campanhas e pontos. Dados ainda não são publicados ao produtor.

A interface verifica se os pontos estão dentro de Polygon/MultiPolygon, incluindo exclusão de anéis internos. Essa checagem espacial é feita no navegador; o banco valida os intervalos de coordenadas e os vínculos. Talhões sem limites permitem coordenadas manuais sem checagem espacial. Não há geração automática de malha, escolha automática de densidade, resultados laboratoriais ou recomendações agronômicas nesta versão.

Validação: sintaxe JS, casos espaciais (interior, exterior, borda, anel interno e MultiPolygon), criação/atualização de coleta com papel authenticated e ausência de leitura por usuário sem vínculo. Testes no banco foram executados com rollback. Validação visual no navegador permanece pendente.
