<p align="center">
  <img src="docs/icone.png" width="96" alt="Ícone do GamePing">
</p>

<h1 align="center">GamePing</h1>

<p align="center">
  <b>Monitor e otimizador de conexão para jogos online no Windows</b><br>
  Mede o ping até o servidor da sua partida, mostra onde está o atraso e ajusta o Windows para reduzir picos de lag.
</p>

<p align="center">
  <a href="../../releases/latest"><b>⬇️ Baixar a versão mais recente</b></a>
</p>

---

## O que ele faz

- **Detecta o jogo e o servidor sozinho.** Abra o jogo, entre numa partida e abra o GamePing. Funciona com jogos que usam UDP (CS2, Valorant, Fortnite, Dota 2 e outros). Os demais podem ser escolhidos numa lista.
- **Ping ao vivo por cima do jogo.** Uma janelinha com ping, jitter e perda de pacotes. Dá para ajustar tamanho, transparência e modo mínimo, e mostrar ou esconder com **Ctrl + Shift + P**.
- **Alertas durante a partida.** Avisa quando há perda de pacotes, pico de ping ou algum programa fazendo download pesado em segundo plano.
- **Diagnóstico.** Compara o ping até o seu roteador com o ping até o servidor e diz se o problema está no Wi-Fi ou roteador, no provedor ou na distância.
- **Rota (traceroute).** Mostra cada roteador no caminho e em qual trecho o ping aumenta.
- **Regiões do CS2.** Pinga todas as regiões de servidores da Valve e sugere o melhor valor para o *Ping máximo aceitável no matchmaking*.
- **Otimizações do Windows, sempre reversíveis:**
  - prioridade QoS para o jogo;
  - desativar a limitação de rede do Windows;
  - desativar o Nagle (envio imediato de pacotes TCP);
  - desligar a economia de energia e o Interrupt Moderation da placa de rede;
  - pausar o Windows Update durante a partida.
- **Histórico por partida.** Grava ping, jitter e perda de cada partida e compara as partidas com e sem otimizações.
- **Relatório para o provedor.** Mede a conexão por 1 minuto e gera um relatório pronto para mandar ao suporte da sua operadora.
- **Teste de bufferbloat.** Mede quanto o ping sobe quando alguém está usando a internet.
- **Tema escuro, ícone perto do relógio e opção de iniciar com o Windows.**
- **Atualização com um clique.** O GamePing avisa quando sai uma versão nova, baixa e confere o instalador antes de abrir.

## Instalação

1. Baixe o **`GamePing-Instalador-x.y.z.exe`** em [Releases](../../releases/latest).
2. Execute e siga os passos. O GamePing precisa de **permissão de administrador** para monitorar o tráfego de rede e aplicar as otimizações.
3. O Windows pode mostrar **"O Windows protegeu o computador"**, porque o programa ainda não tem assinatura digital. Clique em **Mais informações → Executar assim mesmo**.

**Requisitos:** Windows 10 ou 11 de 64 bits. Não precisa instalar o .NET, ele já vem incluído.

**Dica para a sobreposição:** ela só aparece por cima de jogos em modo **"Tela cheia em janela"** (ou "Janela sem bordas"). No CS2: *Configurações → Vídeo → Modo de exibição*.

## Segurança e anti-cheat

O GamePing **não mexe no jogo**: não injeta código, não lê a memória do jogo e não altera os pacotes dele. Ele só **observa** o tráfego de rede pelo próprio monitor do Windows (ETW) e ajusta configurações do sistema. Por isso não há risco com sistemas anti-cheat.

Todas as otimizações guardam o valor original antes de mudar qualquer coisa. Você pode desfazer tudo pelo botão **"Restaurar tudo ao original"**. Ao desinstalar, tudo também é revertido automaticamente.

## Privacidade

O GamePing não tem conta, anúncios nem telemetria. Histórico, configurações e relatórios ficam só no seu PC. As únicas conexões que ele faz além dos pings são:

- a lista pública de regiões da Valve (`api.steampowered.com`), para a aba *Regiões (CS2)*;
- um download de teste da Cloudflare (`speed.cloudflare.com`), só quando você roda o teste de bufferbloat;
- a página de versões deste repositório (`api.github.com`), no máximo uma vez por dia, para avisar quando sai uma versão nova. Dá para desligar em *Opções → Atualizações*.

## Desinstalar

Use **Configurações → Aplicativos → GamePing → Desinstalar** (ou "Adicionar ou remover programas"). A desinstalação reverte as otimizações, religa o Windows Update se ele estiver pausado e remove o início automático. No final, ela pergunta se você quer apagar também o histórico e as configurações.

## Problemas?

Abra uma [issue](../../issues) descrevendo o que aconteceu e anexe o arquivo de registro. Ele fica em **GamePing → Opções → Abrir registro de erros**.

---

<sub>GamePing é gratuito. Veja os [termos de uso](TERMOS.md).</sub>
