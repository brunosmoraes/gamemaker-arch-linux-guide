1. **Instalando o `debtap`**:
   - O `debtap` é uma ferramenta que permite converter pacotes `.deb` (formato usado pelo Debian/Ubuntu) para pacotes Arch Linux.
   - Para instalá-lo, execute:
     ```
     yay -S debtap
     ```

2. **Criando o pacote Arch**:
   - Navegue até o diretório onde você baixou o GameMaker Studio.
   - Execute os seguintes comandos para criar o pacote Arch:
     ```
     cd <caminho onde você baixou o GameMaker>
     sudo debtap -u
     debtap GameMakerStudio2-Beta-23.1.1.329.deb
     ```

3. **Instalando o pacote Arch**:
   - Agora, instale o pacote Arch gerado:
     ```
     sudo pacman -U gamemakerstudio2-beta-23.1.1.329-1-any.pkg.tar.zst
     ```

4. **Steam Runtimes**:
   - O Steam Runtimes é um conjunto de bibliotecas e ambientes de tempo de execução usados pelo Steam para garantir a compatibilidade com jogos e aplicativos.
   - Para instalá-lo:
     - Crie o diretório para o Steam Runtimes:
       ```
       sudo mkdir /opt/steam-runtime/
       ```
     - Baixe e extraia o pacote do Steam Runtimes:
       ```
       curl https://repo.steampowered.com/steamrt-images-scout/snapshots/latest-steam-client-general-availability/com.valvesoftware.SteamRuntime.Sdk-amd64,i386-scout-sysroot.tar.gz | sudo tar -xzf - -C /opt/steam-runtime/
       ```
     - Você pode controlar onde o runtime é instalado modificando o caminho final no comando acima. No entanto, se fizer isso, também será necessário alterar as configurações do Ubuntu nas preferências do GameMaker.

5. **Ferramentas de Empacotamento**:
   - O `linuxdeploy` e o `appimagetool` são ferramentas para criar pacotes AppImage para aplicativos Linux.
   - Para instalá-las:
     ```
     wget https://github.com/linuxdeploy/linuxdeploy/releases/download/continuous/linuxdeploy-x86_64.AppImage
     sudo install -m 0755 linuxdeploy-x86_64.AppImage /usr/local/bin/linuxdeploy

     wget https://github.com/AppImage/AppImageKit/releases/download/continuous/appimagetool-x86_64.AppImage
     sudo install -m 0755 appimagetool-x86_64.AppImage /usr/local/bin/appimagetool
     ```

