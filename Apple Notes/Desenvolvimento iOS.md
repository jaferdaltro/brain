---
apple-notes-id: BD7BC3CB-9F1C-43EB-BB0B-5857466710EF
---
1. Criando o projeto iOS:
		Abra o Xcode e selecione "Create a new Xcode project";
			- Escolha a opção "App" sob a categoria "iOS";
			- Nomeie seu projeto, escolha uma organização e um identificador. Garanta que a linguagem seja "Swift" e a interface seja "Storyboard".
			- Configure as principais opções de projeto:
		Destinos suportados;
				- Versão mínima do iOS para publicação;
				- Identificação (para publicar um aplicativo e instalá-lo no celular, é necessário ter uma identificação da Apple Developer Account);
				- Informações de publicação: defina a orientação do iPhone - Portrait ou Landscape?
1. Entenda os principais arquivos gerados:
		AppDelegate - Controla o ciclo de vida da aplicação;
			- SceneDelegate - Introduzido no iOS 13, gerencia "cenários" ou instâncias da UI;
			- ViewController - É a tela inicial, gerencia a apresentação dos elementos visuais;
			- Main storyboard - Ferramenta visual para construir a UI;
			- Assets - Mantém imagens, cores, ícones do projeto;
			- LaunchScreen - Tela inicial rápida que aparece quando o aplicativo é iniciado;
			- Info - Contém dados e configurações para o sistema interagir com o aplicativo.
1. Importando Imagens e Cores para o Asset Catalog:
		No "AccentColor", modifique a cor para branco;
			- "AppIcon" - Importe o ícone fornecido no material do curso ou do Figma;
			- Adicione a imagem da "Logo". Como está em SVG, ela não perderá qualidade;
			- Importe a imagem do "Casal assistindo TV". Esta é uma imagem PNG, então temos três versões diferentes dela para suportar diferentes dispositivos. Arraste as três versões para o Assets;
			- Adicione duas novas cores:
		BackgroundColor: Use o hexadecimal **\#15053F**;
				- ButtonBackgroundColor: Use o hexadecimal **\#B370FF**.
1. Explorando o Storyboard (Opcional):
		Mesmo focando em view code, é útil saber um pouco sobre o Storyboard. Abra o Main.storyboard;
			- Familiarize-se com a interface. Aqui é onde muitos desenvolvedores fazem layouts utilizando a abordagem visual.