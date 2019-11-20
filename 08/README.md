## Kubernetes ハンズオン 第6回 nginx を sidecar に使用した deployment の作成


### 1. kubernetes-helm インストール

``` bash

~$ brew install kubernetes-helm
Updating Homebrew...
==> Downloading https://homebrew.bintray.com/bottles-portable-ruby/portable-ruby-2.6.3.mavericks.bottle.tar.gz
######################################################################## 100.0%
==> Pouring portable-ruby-2.6.3.mavericks.bottle.tar.gz
==> Auto-updated Homebrew!
Updated 2 taps (homebrew/core and homebrew/cask).
==> New Formulae
adios2                   cartridge-cli            gleam                    kind                     mysql-client@5.7         oauth2l                  pylint                   tweak
alp                      cf-tool                  gmt@5                    kyma-cli                 mysql-connector-c++@1.1  onefetch                 rav1e                    virustotal-cli
appium                   comby                    govc                     liblouis                 navi                     openjdk                  sentencepiece            wagyu
arduino-cli              cups                     grin                     libtensorflow@1          nbdime                   openjdk@11               tdkjs                    wal2json
atasm                    dafny                    grin-wallet              manticoresearch          ngt                      openjdk@12               tektoncd-cli             xgboost
awsume                   diffr                    helm@2                   minikube                 node@12                  pnetcdf                  toast
bingrep                  dvc                      javacc                   mpi4py                   notifiers                pnpm                     trader
calceph                  git-delta                jd                       mpv                      numpy@1.16               prestosql                ttyplot
==> Updated Formulae
kubectx ✔                        darksky-weather                  go@1.12                          libvoikko                        pgcli                            ssldump
kubernetes-cli ✔                 dartsim                          gobby                            libxml2                          pgformatter                      stanford-corenlp
kustomize ✔                      dasm                             gocryptfs                        libxmlsec1                       pgloader                         stanford-ner
mysql ✔                          dav1d                            godep                            libxslt                          pgrouting                        starship
ruby-build ✔                     dbhash                           goffice                          libzdb                           pgweb                            stella
sqlite ✔                         dcm2niix                         golang-migrate                   lightning                        phoronix-test-suite              stellar-core
abcm2ps                          dcmtk                            gomplate                         linkerd                          php                              step
abcmidi                          dcos-cli                         goofys                           links                            php-code-sniffer                 stgit
ack                              deark                            goreleaser                       llvm                             php-cs-fixer                     stone-soup
acpica                           deno                             goreman                          llvm@6                           php@7.1                          stormssh
admesh                           dependency-check                 gradio                           llvm@7                           php@7.2                          stress-ng
adwaita-icon-theme               deployer                         gradle                           llvm@8                           phpmyadmin                       subversion
aespipe                          devspace                         grafana                          lmod                             phpstan                          suil
alexjs                           dhall                            grails                           logstash                         phpunit                          suite-sparse
aliyun-cli                       dhall-bash                       graphviz                         logtalk                          picard-tools                     sundials
amazon-ecs-cli                   dhall-json                       groonga                          lsdvd                            pioneer                          supervisor
ammonite-repl                    di                               grpc                             luarocks                         plantuml                         suricata
ampl-mp                          diamond                          grt                              lxc                              platformio                       svgo
amtk                             diff-pdf                         gsmartcontrol                    macvim                           pmd                              swagger-codegen
angle-grinder                    diffoscope                       gspell                           magic-wormhole                   poco                             swagger-codegen@2
angular-cli                      dita-ot                          gtk+3                            mame                             ponyc                            swaks
anime-downloader                 dive                             gtk-gnutella                     mapserver                        poppler                          swift-protobuf
anjuta                           django-completion                gtk-mac-integration              mariadb                          potrace                          swiftformat
annie                            dmd                              gtkmm3                           mariadb-connector-c              ppsspp                           swiftlint
ansible                          dmtx-utils                       gtksourceview3                   mariadb-connector-odbc           pqiv                             sxiv
ansible@1.9                      dnscrypt-proxy                   gtksourceview4                   mariadb@10.1                     pre-commit                       syncthing
ansible@2.0                      dnsperf                          gtksourceviewmm3                 mariadb@10.2                     prefixsuffix                     sysbench
ansifilter                       docfx                            gtkspell3                        mariadb@10.3                     prettier                         taskell
antibody                         docker                           gtranslator                      math-comp                        procs                            tbb
apache-arrow                     docker-completion                gupnp-tools                      maxwell                          profanity                        tcpdump
apache-arrow-glib                docker-compose                   h2                               mdbook                           proguard                         telegraf
apache-flink                     docker-machine-nfs               h3                               memcached                        proj                             teleport
apache-zeppelin                  docker-squash                    handbrake                        mercurial                        prometheus                       tenyr
appscale-tools                   doctl                            haproxy                          meson                            proteinortho                     tepl
arangodb                         doitlive                         harfbuzz                         metaproxy                        protobuf                         termshark
aria2                            dosbox-x                         haxe                             metricbeat                       protobuf-c                       termtosvg
armadillo                        dovecot                          hcloud                           mgba                             prototool                        terraform
arp-scan                         drafter                          helmfile                         micronaut                        pspg                             terraformer
artifactory                      drone-cli                        helmsman                         mill                             pulumi                           terragrunt
asdf                             duo_unix                         hexyl                            minica                           putty                            terrahub
ask-cli                          duplicity                        hfstospell                       minio                            puzzles                          texinfo
aspell                           dust                             hg-fast-export                   minio-mc                         py2cairo                         tfenv
assimp                           dvdauthor                        highlight                        minizinc                         py3cairo                         tflint
atlantis                         dvdbackup                        hlint                            minizip2                         pybind11                         theharvester
atlassian-cli                    dxpy                             homebank                         mint                             pyenv                            thrift@0.9
auditbeat                        dynare                           html-xml-utils                   mitmproxy                        pyqt                             tile38
augustus                         eccodes                          htmldoc                          mkcert                           pyside                           tintin
aws-cdk                          elasticsearch                    hub                              mkl-dnn                          python                           tmate
aws-google-auth                  eless                            hugo                             mkvtoolnix                       python-yq                        tmuxinator
aws-okta                         elixir                           hwloc                            mm-common                        python@2                         tmuxinator-completion
aws-sdk-cpp                      embulk                           hydra                            mmark                            qalculate-gtk                    tnef
awscli                           envconsul                        hyperfine                        modgit                           qbs                              tokei
axel                             eprover                          hyperscan                        monero                           qemu                             tomcat
azure-cli                        erlang                           hypre                            mongoose                         qhull                            tomcat@8
b2-tools                         erlang@20                        i2p                              mono-libgdiplus                  qjackctl                         topgrade
babel                            erlang@21                        i2pd                             mosh                             qpdf                             tor
badtouch                         eslint                           ical-buddy                       mpd                              qscintilla2                      tox
balena-cli                       esptool                          icdiff                           mpg123                           qstat                            traefik
ballerina                        etcd                             ice                              mpich                            qt                               traefik@1
baobab                           ethereum                         icemon                           mpop                             quex                             trafficserver
bazel                            ettercap                         igv                              msmtp                            quickjs                          triton
bazelisk                         evince                           imagemagick                      mvnvm                            quicktype                        tundra
bear                             exercism                         imagemagick@6                    mydumper                         qxmpp                            tunnel
bedops                           exiftool                         imageoptim-cli                   mypy                             rabbitmq                         twine-pypi
bee                              exploitdb                        imapfilter                       mysql++                          rancher-cli                      two-lame
benthos                          eye-d3                           influxdb                         mysql-client                     rancid                           typescript
berglas                          faas-cli                         inform6                          mysql-connector-c++              rclone                           u-boot-tools
bettercap                        fabio                            inlets                           mysql@5.6                        rdesktop                         ucloud
bibutils                         fabric                           innotop                          mysql@5.7                        re-flex                          um
bind                             faudio                           insect                           mysqltuner                       re2                              unbound
binwalk                          fauna-shell                      instead                          mytop                            redis                            uncrustify
bit                              fdk-aac                          io                               n                                redpen                           ungit
bitrise                          fdroidserver                     ios-webkit-debug-proxy           nano                             remind                           unoconv
bitwarden-cli                    fetchmail                        ipbt                             nanopb-generator                 reminiscence                     unrar
black                            ffmpeg                           ipmiutil                         nats-server                      repo                             urh
blink1                           ffmpeg@2.8                       iproute2mac                      ne                               reposurgeon                      urweb
blockhash                        ffmpegthumbnailer                ipv6calc                         neatvi                           residualvm                       v2ray-plugin
bluepill                         ffsend                           iso-codes                        needle                           restic                           v8
bnd                              fibjs                            ispc                             neko                             restview                         vagrant-completion
bogofilter                       fig2dev                          istioctl                         neo4j                            rethinkdb                        vala
boost-mpi                        file-roller                      itk                              neomutt                          rex                              vamp-plugin-sdk
boost-python                     firebase-cli                     janet                            neovim                           rgbds                            vapoursynth
boost-python3                    flake8                           jena                             netdata                          riemann                          vapoursynth-imwri
boot-clj                         flatcc                           jenkins                          netlify-cli                      rke                              vapoursynth-ocr
borgmatic                        flintrock                        jenkins-lts                      newman                           rocksdb                          vapoursynth-sub
botan                            flow                             jetty                            newsboat                         rom-tools                        varnish
bro                              fluid-synth                      jfrog-cli-go                     nghttp2                          root                             vault
broot                            fluxctl                          jhipster                         nifi                             roswell                          velero
buildkit                         flyway                           jmeter                           nim                              rpm                              verilator
buku                             fmt                              jo                               nlohmann-json                    rrdtool                          vert.x
bulk_extractor                   fn                               joplin                           nnn                              rust                             vfuse
bullet                           folly                            jruby                            node                             rustup-init                      vim
bundletool                       fontforge                        jsvc                             node-build                       s3-backer                        vim@7.4
bup                              fonttools                        juju                             node@10                          s3ql                             vips
bvi                              fop                              just                             node@8                           s6                               virgil
byacc                            fork-cleaner                     jvgrep                           node_exporter                    salt                             virtuoso
byteman                          fossil                           k3d                              nodenv                           saxon                            vit
bzt                              freerdp                          kafka                            nomad                            sbcl                             volatility
caddy                            freeswitch                       kallisto                         notmuch                          sbjson                           vte3
caf                              fribidi                          kcov                             now-cli                          sbt                              vtk
caffe                            frpc                             kerl                             nspr                             scalaenv                         vulkan-headers
calcurse                         frps                             kitchen-sync                     nss                              scamper                          wartremover
calicoctl                        frugal                           klavaro                          ntl                              scc                              watchexec
cargo-completion                 fselect                          kompose                          ntopng                           sccache                          watson
carla                            fstrm                            kops                             nu                               scipy                            webpack
carrot2                          futhark                          kotlin                           nuget                            scrcpy                           whois
carthage                         fwup                             kpcli                            numpy                            screen                           wireguard-go
cash-cli                         fx                               ksh                              nushell                          screenfetch                      wireguard-tools
catch2                           fzf                              ktlint                           nut                              scummvm                          wireshark
cayley                           gammu                            kube-aws                         nvm                              scummvm-tools                    wolfssl
ccache                           gatsby-cli                       kubeaudit                        ocrmypdf                         sdlpop                           wp-cli
ccm                              gcab                             kubebuilder                      octant                           serd                             wp-cli-completion
ceres-solver                     gdal                             kubecfg                          octave                           serf                             wsk
cern-ndiff                       gdcm                             kubeless                         odpi                             serverless                       wtf
certbot                          gdk-pixbuf                       kubeprod                         offlineimap                      sfk                              wtfutil
cfn-lint                         gdl                              kubeseal                         ola                              sfst                             wxmaxima
cfr-decompiler                   geckodriver                      lazydocker                       omega                            shadowenv                        x264
cfssl                            gedit                            lazygit                          ooniprobe                        shadowsocks-libev                x265
cgal                             geoipupdate                      legit                            opa                              shairport-sync                   xa
chafa                            geos                             lego                             open-babel                       shared-mime-info                 xapian
chamber                          gerbv                            leptonica                        open-mpi                         ship                             xcodegen
charm-tools                      ghex                             lerna                            open-zwave                       shogun                           xonsh
cheat                            ghostscript                      libcaca                          openapi-generator                silk                             xorriso
check                            ghq                              libcapn                          opencoarrays                     simgrid                          xpdf
checkbashisms                    giflib                           libcouchbase                     opencv                           simple-scan                      xplanet
checkstyle                       gifski                           libdazzle                        openimageio                      singular                         xrootd
chromaprint                      ginac                            libdvdnav                        openjazz                         sip                              xsimd
cimg                             git                              libdvdread                       openrct2                         siril                            xtensor
clac                             git-annex                        libedit                          openssh                          sispmctl                         xxhash
clamav                           git-archive-all                  libetpan                         opentracing-cpp                  skaffold                         yacas
clang-format                     git-cola                         libevhtp                         openvdb                          skafos                           yadm
cli53                            git-quick-stats                  libfabric                        openvpn                          ski                              yafc
clib                             git-revise                       libgweather                      operator-sdk                     skopeo                           yaml-cpp
cloc                             git-town                         libheif                          orc-tools                        slowhttptest                     yamllint
clojure                          gitfs                            libical                          osm-gps-map                      smali                            yara
clutter-gtk                      gitg                             libimobiledevice                 osmium-tool                      snakemake                        yarn
cmake                            gitlab-gem                       libjwt                           osqp                             snapcraft                        yash
cmatrix                          gitlab-runner                    liblockfile                      osquery                          solr                             yaz
cnats                            gitleaks                         libmaxminddb                     ott                              sonar-scanner                    ykman
cocoapods                        gitless                          libming                          oxipng                           sonarqube                        yle-dl
cointop                          gitmoji                          libopenmpt                       p11-kit                          sonobuoy                         youtube-dl
collectd                         gitup                            libpcap                          packer                           sops                             yq
composer                         gitversion                       libpeas                          pagmo                            sord                             zabbix
conan                            gjs                              libphonenumber                   paket                            source-highlight                 zbackup
confluent-platform               glade                            libplist                         pango                            source-to-image                  zbar
conjure-up                       glances                          libpulsar                        parallel                         sourcedocs                       zint
console_bridge                   glib                             librdkafka                       pastel                           sourcekitten                     zita-convolver
consul-template                  glib-networking                  librealsense                     pdal                             sparkey                          znc
contentful-cli                   glooctl                          libressl                         pdf2htmlex                       sparse                           zola
convox                           gmic                             librsvg                          pdf2json                         spatialindex                     zookeeper
coq                              gmime                            librsync                         pdfcpu                           spdlog                           zrepl
couchdb                          gmt                              libsass                          pdftk-java                       sphinx-doc                       zsh-completions
cromwell                         gnome-builder                    libslax                          pdftoipe                         spice-gtk                        zsh-history-substring-search
crystal                          gnome-latex                      libsoup                          percona-server                   spigot                           zshdb
csvq                             gnome-recipes                    libspectre                       percona-toolkit                  sqldiff                          zstd
curl                             gnumeric                         libssh                           percona-xtrabackup               sqlite-analyzer                  zydis
curl-openssl                     gnunet                           libstrophe                       perl-build                       sqlmap
cutter                           gnuradio                         libtensorflow                    perltidy                         squid
cypher-shell                     gnutls                           libtiff                          petsc                            sratom
cython                           go                               libtommath                       petsc-complex                    sratoolkit
dark-mode                        go-bindata                       libvirt                          pgbadger                         ssh-audit
==> Renamed Formulae
jupyter -> jupyterlab                             kubernetes-helm -> helm                           presto -> prestodb                                usbmuxd -> libusbmuxd
==> Deleted Formulae
aiccu                       dcal                        gmt@4                       hana                        mysql-connector-c           protobuf@3.1                ruby@2.0
bdsup2sub                   erlang@17                   gmtl                        llvm@4                      mysql@5.5                   raine                       supersonic
cockroach                   erlang@19                   grib-api                    mariadb@10.0                pound                       riak                        wine
==> minikube has been moved to Homebrew.
To uninstall the cask run:
  brew cask uninstall --force minikube
==> Installing minikube...
==> Installing dependencies for minikube: kubernetes-cli
==> Installing minikube dependency: kubernetes-cli
==> Downloading https://homebrew.bintray.com/bottles/kubernetes-cli-1.16.3.high_sierra.bottle.tar.gz
==> Downloading from https://akamai.bintray.com/a9/a97a579a2adaa9720aa122355b0a43cbebea49da394f3489a300f41d8d5e7f77?__gda__=exp=1574270940~hmac=34deb46c4ac52f71d4b8bbcb6e1d2a8449554c87337bc60ad6b6f17c
######################################################################## 100.0%
==> Pouring kubernetes-cli-1.16.3.high_sierra.bottle.tar.gz
==> Caveats
Bash completion has been installed to:
  /usr/local/etc/bash_completion.d

zsh completions have been installed to:
  /usr/local/share/zsh/site-functions
==> Summary
🍺  /usr/local/Cellar/kubernetes-cli/1.16.3: 232 files, 52.3MB
==> Installing minikube
==> Downloading https://homebrew.bintray.com/bottles/minikube-1.5.2.high_sierra.bottle.tar.gz
==> Downloading from https://akamai.bintray.com/5c/5c5d913c4cd18463ab10384d35fc59624e678874d8219cbc5af3b88a17eb89d8?__gda__=exp=1574270944~hmac=ceb717e4a1d9fea5a4d2e43a4e3d5b93b7f72085bc9f4a4f3df5ab2b
######################################################################## 100.0%
==> Pouring minikube-1.5.2.high_sierra.bottle.tar.gz
==> minikube cask is installed, skipping link.
==> Caveats
Bash completion has been installed to:
  /usr/local/etc/bash_completion.d

zsh completions have been installed to:
  /usr/local/share/zsh/site-functions
==> Summary
🍺  /usr/local/Cellar/minikube/1.5.2: 8 files, 51.5MB
==> `brew cleanup` has not been run in 30 days, running now...
Removing: /Users/jiraffe40095/Library/Caches/Homebrew/kubectx--0.7.0.tar.gz... (472.6KB)
Removing: /usr/local/Cellar/kubernetes-cli/1.16.0... (232 files, 52.3MB)
Removing: /Users/jiraffe40095/Library/Caches/Homebrew/kubernetes-cli--1.16.0.high_sierra.bottle.tar.gz... (14.4MB)
Removing: /Users/jiraffe40095/Library/Caches/Homebrew/sqlite--3.29.0.high_sierra.bottle.tar.gz... (1.9MB)
Removing: /Users/jiraffe40095/Library/Logs/Homebrew/ruby-build... (2 files, 179B)
Removing: /Users/jiraffe40095/Library/Logs/Homebrew/openssl@1.1... (64B)
Removing: /Users/jiraffe40095/Library/Logs/Homebrew/kubectx... (103B)
Removing: /Users/jiraffe40095/Library/Logs/Homebrew/kubernetes-cli... (64B)
Removing: /Users/jiraffe40095/Library/Logs/Homebrew/rbenv... (64B)
Pruned 0 symbolic links and 117 directories from /usr/local
Error: Permission denied @ apply2files - /usr/local/share/Library/Caches/Yarn/v4/npm-vue-2.5.17-0f8789ad718be68ca1872629832ed533589c6ada/node_modules/vue/src/platforms/weex/.DS_Store
Linking /usr/local/Cellar/minikube/1.5.2... 3 symlinks created

==> Downloading https://homebrew.bintray.com/bottles/helm-3.0.0.high_sierra.bottle.tar.gz
==> Downloading from https://akamai.bintray.com/67/67e98c512b73b5bc99ef3d6fe8c58a397fadfd09e8697b2aeccb463977c2a6d4?__gda__=exp=1574270958~hmac=a71e1a7dc25ac9c90f476098f4a71a432727d9a8b7784a02ec554edd
######################################################################## 100.0%
==> Pouring helm-3.0.0.high_sierra.bottle.tar.gz
==> Caveats
Bash completion has been installed to:
  /usr/local/etc/bash_completion.d

zsh completions have been installed to:
  /usr/local/share/zsh/site-functions
==> Summary
🍺  /usr/local/Cellar/helm/3.0.0: 7 files, 40.6MB
==> `brew cleanup` has not been run in 30 days, running now...
Error: Permission denied @ apply2files - /usr/local/share/Library/Caches/Yarn/v4/npm-vue-2.5.17-0f8789ad718be68ca1872629832ed533589c6ada/node_modules/vue/src/platforms/weex/.DS_Store

~$ brew doctor
Your system is ready to brew.

~$ mkdir local
~$ cd local/

# 以下よりインストール用コマンドをコピーし実行
# https://github.com/Homebrew/brew/blob/master/docs/Installation.md#alternative-installs

~$ mkdir homebrew && curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew
~$ ls -l homebrew/
total 72
-rw-r--r--   1 jiraffe40095  staff    98 11 21 00:12 CHANGELOG.md
-rw-r--r--   1 jiraffe40095  staff   831 11 21 00:12 CONTRIBUTING.md
-rw-r--r--   1 jiraffe40095  staff  1357 11 21 00:12 Dockerfile
-rw-r--r--   1 jiraffe40095  staff   739 11 21 00:12 Dockerfile.yml
-rw-r--r--   1 jiraffe40095  staff  1334 11 21 00:12 LICENSE.txt
drwxr-xr-x   9 jiraffe40095  staff   288 11 21 00:12 Library
-rw-r--r--   1 jiraffe40095  staff  8472 11 21 00:12 README.md
-rw-r--r--   1 jiraffe40095  staff   704 11 21 00:12 SECURITY.md
drwxr-xr-x   3 jiraffe40095  staff    96 11 21 00:12 bin
drwxr-xr-x   6 jiraffe40095  staff   192 11 21 00:12 completions
drwxr-xr-x  53 jiraffe40095  staff  1696 11 21 00:12 docs
drwxr-xr-x   5 jiraffe40095  staff   160 11 21 00:12 manpages

# ~/.bashrc に以下追記
`export PATH=$HOME/local/homebrew/bin:$PATH`
`export HOMEBREW_CACHE=$HOME/local/homebrew/cache`


~$ which brew
/Users/jiraffe40095/local/homebrew/bin/brew
~$ brew --version
==> Downloading https://homebrew.bintray.com/bottles-portable-ruby/portable-ruby-2.6.3.mavericks.bottle.tar.gz
######################################################################## 100.0%
==> Pouring portable-ruby-2.6.3.mavericks.bottle.tar.gz
Homebrew >=1.7.1 (shallow or no git repository)
Homebrew/homebrew-core N/A

```

```
# 改めて brew install kubernetes-helm 実行

Initialized empty Git repository in /Users/jiraffe40095/local/homebrew/.git/
Updating Homebrew...
remote: Enumerating objects: 45, done.
remote: Counting objects: 100% (45/45), done.
remote: Compressing objects: 100% (45/45), done.
remote: Total 128913 (delta 1), reused 36 (delta 0), pack-reused 128868
Receiving objects: 100% (128913/128913), 30.74 MiB | 6.69 MiB/s, done.
Resolving deltas: 100% (94601/94601), done.
From https://github.com/Homebrew/brew
 * [new branch]      master     -> origin/master
remote: Enumerating objects: 36, done.
remote: Counting objects: 100% (36/36), done.
remote: Compressing objects: 100% (36/36), done.
remote: Total 36 (delta 0), reused 36 (delta 0), pack-reused 0
Unpacking objects: 100% (36/36), done.
 * [new tag]             0.1        -> 0.1
 * [new tag]             0.2        -> 0.2
 * [new tag]             0.3        -> 0.3
 * [new tag]             0.4        -> 0.4
 * [new tag]             0.5        -> 0.5
 * [new tag]             0.6        -> 0.6
 * [new tag]             0.7        -> 0.7
 * [new tag]             0.7.1      -> 0.7.1
 * [new tag]             0.8        -> 0.8
 * [new tag]             0.8.1      -> 0.8.1
 * [new tag]             0.9        -> 0.9
 * [new tag]             0.9.1      -> 0.9.1
 * [new tag]             0.9.2      -> 0.9.2
 * [new tag]             0.9.3      -> 0.9.3
 * [new tag]             0.9.4      -> 0.9.4
 * [new tag]             0.9.5      -> 0.9.5
 * [new tag]             0.9.8      -> 0.9.8
 * [new tag]             0.9.9      -> 0.9.9
 * [new tag]             1.0.0      -> 1.0.0
 * [new tag]             1.0.1      -> 1.0.1
 * [new tag]             1.0.2      -> 1.0.2
 * [new tag]             1.0.3      -> 1.0.3
 * [new tag]             1.0.4      -> 1.0.4
 * [new tag]             1.0.5      -> 1.0.5
 * [new tag]             1.0.6      -> 1.0.6
 * [new tag]             1.0.7      -> 1.0.7
 * [new tag]             1.0.8      -> 1.0.8
 * [new tag]             1.0.9      -> 1.0.9
 * [new tag]             1.1.0      -> 1.1.0
 * [new tag]             1.1.1      -> 1.1.1
 * [new tag]             1.1.10     -> 1.1.10
 * [new tag]             1.1.11     -> 1.1.11
 * [new tag]             1.1.12     -> 1.1.12
 * [new tag]             1.1.13     -> 1.1.13
 * [new tag]             1.1.2      -> 1.1.2
 * [new tag]             1.1.3      -> 1.1.3
 * [new tag]             1.1.4      -> 1.1.4
 * [new tag]             1.1.5      -> 1.1.5
 * [new tag]             1.1.6      -> 1.1.6
 * [new tag]             1.1.7      -> 1.1.7
 * [new tag]             1.1.8      -> 1.1.8
 * [new tag]             1.1.9      -> 1.1.9
 * [new tag]             1.2.0      -> 1.2.0
 * [new tag]             1.2.1      -> 1.2.1
 * [new tag]             1.2.2      -> 1.2.2
 * [new tag]             1.2.3      -> 1.2.3
 * [new tag]             1.2.4      -> 1.2.4
 * [new tag]             1.2.5      -> 1.2.5
 * [new tag]             1.2.6      -> 1.2.6
 * [new tag]             1.3.0      -> 1.3.0
 * [new tag]             1.3.1      -> 1.3.1
 * [new tag]             1.3.2      -> 1.3.2
 * [new tag]             1.3.3      -> 1.3.3
 * [new tag]             1.3.4      -> 1.3.4
 * [new tag]             1.3.5      -> 1.3.5
 * [new tag]             1.3.6      -> 1.3.6
 * [new tag]             1.3.7      -> 1.3.7
 * [new tag]             1.3.8      -> 1.3.8
 * [new tag]             1.3.9      -> 1.3.9
 * [new tag]             1.4.0      -> 1.4.0
 * [new tag]             1.4.1      -> 1.4.1
 * [new tag]             1.4.2      -> 1.4.2
 * [new tag]             1.4.3      -> 1.4.3
 * [new tag]             1.5.0      -> 1.5.0
 * [new tag]             1.5.1      -> 1.5.1
 * [new tag]             1.5.10     -> 1.5.10
 * [new tag]             1.5.11     -> 1.5.11
 * [new tag]             1.5.12     -> 1.5.12
 * [new tag]             1.5.13     -> 1.5.13
 * [new tag]             1.5.14     -> 1.5.14
 * [new tag]             1.5.2      -> 1.5.2
 * [new tag]             1.5.3      -> 1.5.3
 * [new tag]             1.5.4      -> 1.5.4
 * [new tag]             1.5.5      -> 1.5.5
 * [new tag]             1.5.6      -> 1.5.6
 * [new tag]             1.5.7      -> 1.5.7
 * [new tag]             1.5.8      -> 1.5.8
 * [new tag]             1.5.9      -> 1.5.9
 * [new tag]             1.6.0      -> 1.6.0
 * [new tag]             1.6.1      -> 1.6.1
 * [new tag]             1.6.10     -> 1.6.10
 * [new tag]             1.6.11     -> 1.6.11
 * [new tag]             1.6.12     -> 1.6.12
 * [new tag]             1.6.13     -> 1.6.13
 * [new tag]             1.6.14     -> 1.6.14
 * [new tag]             1.6.15     -> 1.6.15
 * [new tag]             1.6.16     -> 1.6.16
 * [new tag]             1.6.17     -> 1.6.17
 * [new tag]             1.6.2      -> 1.6.2
 * [new tag]             1.6.3      -> 1.6.3
 * [new tag]             1.6.4      -> 1.6.4
 * [new tag]             1.6.5      -> 1.6.5
 * [new tag]             1.6.6      -> 1.6.6
 * [new tag]             1.6.7      -> 1.6.7
 * [new tag]             1.6.8      -> 1.6.8
 * [new tag]             1.6.9      -> 1.6.9
 * [new tag]             1.7.0      -> 1.7.0
 * [new tag]             1.7.1      -> 1.7.1
 * [new tag]             1.7.2      -> 1.7.2
 * [new tag]             1.7.3      -> 1.7.3
 * [new tag]             1.7.4      -> 1.7.4
 * [new tag]             1.7.5      -> 1.7.5
 * [new tag]             1.7.6      -> 1.7.6
 * [new tag]             1.7.7      -> 1.7.7
 * [new tag]             1.8.0      -> 1.8.0
 * [new tag]             1.8.1      -> 1.8.1
 * [new tag]             1.8.2      -> 1.8.2
 * [new tag]             1.8.3      -> 1.8.3
 * [new tag]             1.8.4      -> 1.8.4
 * [new tag]             1.8.5      -> 1.8.5
 * [new tag]             1.8.6      -> 1.8.6
 * [new tag]             1.9.0      -> 1.9.0
 * [new tag]             1.9.1      -> 1.9.1
 * [new tag]             1.9.2      -> 1.9.2
 * [new tag]             1.9.3      -> 1.9.3
 * [new tag]             2.0.0      -> 2.0.0
 * [new tag]             2.0.1      -> 2.0.1
 * [new tag]             2.0.2      -> 2.0.2
 * [new tag]             2.0.3      -> 2.0.3
 * [new tag]             2.0.4      -> 2.0.4
 * [new tag]             2.0.5      -> 2.0.5
 * [new tag]             2.0.6      -> 2.0.6
 * [new tag]             2.1.0      -> 2.1.0
 * [new tag]             2.1.1      -> 2.1.1
 * [new tag]             2.1.10     -> 2.1.10
 * [new tag]             2.1.11     -> 2.1.11
 * [new tag]             2.1.12     -> 2.1.12
 * [new tag]             2.1.13     -> 2.1.13
 * [new tag]             2.1.14     -> 2.1.14
 * [new tag]             2.1.15     -> 2.1.15
 * [new tag]             2.1.16     -> 2.1.16
 * [new tag]             2.1.2      -> 2.1.2
 * [new tag]             2.1.3      -> 2.1.3
 * [new tag]             2.1.4      -> 2.1.4
 * [new tag]             2.1.5      -> 2.1.5
 * [new tag]             2.1.6      -> 2.1.6
 * [new tag]             2.1.7      -> 2.1.7
 * [new tag]             2.1.8      -> 2.1.8
 * [new tag]             2.1.9      -> 2.1.9
HEAD is now at fb978a786 Merge pull request #6759 from davidrupp/patch-1
==> Tapping homebrew/core
Cloning into '/Users/jiraffe40095/local/homebrew/Library/Taps/homebrew/homebrew-core'...
remote: Enumerating objects: 5087, done.
remote: Counting objects: 100% (5087/5087), done.
remote: Compressing objects: 100% (4880/4880), done.
remote: Total 5087 (delta 47), reused 318 (delta 10), pack-reused 0
Receiving objects: 100% (5087/5087), 4.15 MiB | 4.41 MiB/s, done.
Resolving deltas: 100% (47/47), done.
Tapped 2 commands and 4868 formulae (5,129 files, 12.8MB).
==> Downloading https://homebrew.bintray.com/bottles/helm-3.0.0.high_sierra.bottle.tar.gz
==> Downloading from https://akamai.bintray.com/67/67e98c512b73b5bc99ef3d6fe8c58a397fadfd09e8697b2aeccb463977c2a6d4?__gda__=exp=1574272269~hmac=2541b1a6b326e4f9ea03ae072bd794297055224ca5bb21c09bd4282e
######################################################################## 100.0%
==> Pouring helm-3.0.0.high_sierra.bottle.tar.gz
==> Caveats
Bash completion has been installed to:
  /Users/jiraffe40095/local/homebrew/etc/bash_completion.d

zsh completions have been installed to:
  /Users/jiraffe40095/local/homebrew/share/zsh/site-functions
==> Summary
🍺  /Users/jiraffe40095/local/homebrew/Cellar/helm/3.0.0: 7 files, 40.6MB
==> `brew cleanup` has not been run in 30 days, running now...

# インストール確認
~$ helm version
version.BuildInfo{Version:"v3.0.0", GitCommit:"e29ce2a54e96cd02ccfce88bee4f58bb6e2a28b6", GitTreeState:"clean", GoVersion:"go1.13.4"}
```

### 2. minikube 立ち上げ
```
~$ minikube start -p koujou08
😄  [koujou08] minikube v1.5.2 on Darwin 10.13.6
✨  Automatically selected the 'hyperkit' driver (alternates: [virtualbox])
💾  Downloading driver docker-machine-driver-hyperkit:
    > docker-machine-driver-hyperkit.sha256: 65 B / 65 B [---] 100.00% ? p/s 0s
    > docker-machine-driver-hyperkit: 10.79 MiB / 10.79 MiB  100.00% 3.83 MiB p
🔑  The 'hyperkit' driver requires elevated permissions. The following commands will be executed:

    $ sudo chown root:wheel /Users/jiraffe40095/.minikube/bin/docker-machine-driver-hyperkit 
    $ sudo chmod u+s /Users/jiraffe40095/.minikube/bin/docker-machine-driver-hyperkit 


Password:
💿  Downloading VM boot image ...
    > minikube-v1.5.1.iso.sha256: 65 B / 65 B [--------------] 100.00% ? p/s 0s
    > minikube-v1.5.1.iso: 143.76 MiB / 143.76 MiB [] 100.00% 10.37 MiB p/s 14s
🔥  Creating hyperkit VM (CPUs=2, Memory=2000MB, Disk=20000MB) ...
🐳  Preparing Kubernetes v1.16.2 on Docker '18.09.9' ...
💾  Downloading kubeadm v1.16.2
💾  Downloading kubelet v1.16.2
🚜  Pulling images ...
🚀  Launching Kubernetes ... 
⌛  Waiting for: apiserver
🏄  Done! kubectl is now configured to use "koujou08"


~$ kubectl config use-context koujou08
Switched to context "koujou08".

```

### 3. mysql インストール
```
# repository 追加
~$ helm repo add stable https://kubernetes-charts.storage.googleapis.com/

~$ helm install stable/mysql
Error: must either provide a name or specify --generate-name

~$ helm install stable/mysql --generate-name --namespace app
NAME: mysql-1574272866
LAST DEPLOYED: Thu Nov 21 03:01:08 2019
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
MySQL can be accessed via port 3306 on the following DNS name from within your cluster:
mysql-1574272866.default.svc.cluster.local

To get your root password run:

    MYSQL_ROOT_PASSWORD=$(kubectl get secret --namespace default mysql-1574272866 -o jsonpath="{.data.mysql-root-password}" | base64 --decode; echo)

To connect to your database:

1. Run an Ubuntu pod that you can use as a client:

    kubectl run -i --tty ubuntu --image=ubuntu:16.04 --restart=Never -- bash -il

2. Install the mysql client:

    $ apt-get update && apt-get install mysql-client -y

3. Connect using the mysql cli, then provide your password:
    $ mysql -h mysql-1574272866 -p

To connect to your database directly from outside the K8s cluster:
    MYSQL_HOST=127.0.0.1
    MYSQL_PORT=3306

    # Execute the following command to route the connection:
    kubectl port-forward svc/mysql-1574272866 3306

    mysql -h ${MYSQL_HOST} -P${MYSQL_PORT} -u root -p${MYSQL_ROOT_PASSWORD}

# パスワード取得
~$ echo $(kubectl -n app get secret --namespace app mysql-1574273510 -o jsonpath="{.data.mysql-root-password}" | base64 --decode; echo) 

```

### 4. ポートフォワード開始
``` 
~$ kubectl -n app get deployment
NAME               READY   UP-TO-DATE   AVAILABLE   AGE
mysql-1574273510   1/1     1            1           29s

~$ kubectl -n app get service
NAME               TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
mysql-1574273510   ClusterIP   10.104.207.137   <none>        3306/TCP   74s

~$ kubectl -n app port-forward svc/mysql-1574273510 3306
Forwarding from 127.0.0.1:3306 -> 3306
Forwarding from [::1]:3306 -> 3306
```


### 5. mysqlコマンドで接続
```
~$ mysql -uroot -p -h127.0.0.1 -P3306
# 手順 4. の最後で取得したパスワードを入力

Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 123
Server version: 5.7.14 MySQL Community Server (GPL)

Copyright (c) 2000, 2019, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```

### 6. リリース削除
```
~$ helm -n app ls
NAME            	NAMESPACE	REVISION	UPDATED                             	STATUS  	CHART      	APP VERSION
mysql-1574273510	app      	1       	2019-11-21 03:11:52.412683 +0900 JST	deployed	mysql-1.4.0	5.7.27

~$ helm -n app delete mysql-1574273510
release "mysql-1574273510" uninstalled

~$ helm -n app ls
NAME	NAMESPACE	REVISION	UPDATED	STATUS	CHART	APP VERSION

~$ kubectl -n app get service
No resources found in app namespace.

~$ kubectl -n app get deployment
No resources found in app namespace.

```

