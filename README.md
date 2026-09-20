# Pluto IPTV

Aplicação web estática, pensada para TVs, que apresenta canais da Pluto TV e uma seleção de IPTV aberta em uma interface navegável pelo controle remoto.

## Recursos

- Categorias e grade de canais carregadas a partir de playlists M3U públicas.
- Alternância entre as listas **Pluto TV** e **IPTV gratuita**.
- Reprodução de transmissões HLS (`.m3u8`) pelo player nativo ou pelo hls.js incorporado.
- Navegação por teclado/controle remoto, com destaque visual do item em foco.
- Busca de canais e controles para avançar, voltar e trocar de canal durante a reprodução.
- Atalhos para Plex e Pluto TV.

## Como executar

Não há dependências nem etapa de compilação. Sirva a pasta por HTTP e abra a página no navegador:

```bash
python3 -m http.server 8080
```

Em seguida, acesse [http://localhost:8080](http://localhost:8080). Também é possível hospedar o arquivo `index.html` em qualquer servidor de arquivos estáticos.

## Uso

1. Aguarde o carregamento da lista inicial da Pluto TV.
2. Use as setas do teclado ou do controle remoto para navegar entre abas, categorias e canais.
3. Pressione **Enter/OK** para abrir um canal.
4. No player, use os controles **Anterior**, **Próximo** e **Voltar**. A tecla **Esc/Voltar** fecha o player.

Na aba **IPTV gratuita**, o aplicativo aceita apenas links HTTPS no formato HLS e descarta URLs que pareçam conter tokens, assinaturas ou credenciais temporárias. A seleção é limitada a 240 canais para manter a navegação leve.

## Fontes de canais

- Pluto TV Brasil: `https://raw.githubusercontent.com/BuddyChewChew/pluto/main/pluto_br.m3u`
- IPTV pública: `https://iptv-org.github.io/iptv/index.m3u`

As listas são buscadas em tempo de execução. Portanto, disponibilidade, catálogo e reprodução dependem das fontes e da conexão de rede; um canal pode deixar de funcionar sem que haja uma alteração neste projeto.

## Estrutura

```text
.
├── index.html  # Aplicação, estilos, hls.js incorporado e lógica de interface
└── README.md   # Esta documentação
```

## Aviso

Use apenas streams públicos ou para os quais você possua autorização. O projeto não hospeda, controla nem garante o conteúdo fornecido pelas playlists externas.
