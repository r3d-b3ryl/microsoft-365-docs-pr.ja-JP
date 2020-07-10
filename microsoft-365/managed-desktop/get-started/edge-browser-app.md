---
title: 新しい Microsoft Edge
description: ''
keywords: ブラウザー、Microsoft Managed Desktop、Microsoft 365、service、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f4bc5f85b21148c5a923ca1fc18879a193191c4b
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094788"
---
# <a name="new-microsoft-edge-app"></a>新しい Microsoft Edge アプリ

新しい[Microsoft Edge ブラウザー](https://www.microsoft.com/edge)は、閲覧時に、プライバシー、生産性、および価値の高い世界クラスのパフォーマンスを提供します。 Microsoft マネージドデスクトップは、お客様の環境に新しいエッジブラウザーを展開するためのパブリックプレビューを提供しています。

## <a name="initial-deployment"></a>初期展開

Microsoft マネージドデスクトップデバイスを新しい Microsoft Edge ブラウザーに移行するには、Microsoft マネージドデスクトップポータルを使用して、IT サポートチケットをファイルに追加します。 チケットをファイル化した後、24時間ごとに展開グループに展開すると、エッジ安定チャネルがテストグループに展開されます。 展開を一時停止するには、別のチケットをファイルに保存する操作を要求します。

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge への更新

Microsoft マネージドデスクトップは、6週間ごとに自動更新される、Microsoft Edge の安定した[チャネル](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel)を展開します。 お客様に最適な環境を実現するために、安定したチャネルでの更新は、Microsoft Edge 製品グループによって[段階的](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout)にロールアウトされています。 Microsoft Edge ベータチャネルは現在使用できません。

Microsoft Edge が正しく更新されるように、Microsoft Edge[更新ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)を変更しないでください。

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップによって管理される設定

Microsoft マネージドデスクトップでは、ブラウザーをセキュリティで保護するために、Microsoft Edge の既定のポリシーセットが作成されています。 既定のブラウザーの設定は次のとおりです。

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 拡張機能

Microsoft マネージドデスクトップデバイス上の Microsoft Edge のセキュリティベースラインは、2つのポリシーを設定して、Chrome 拡張およびセキュリティで保護されたエンドユーザーをすべて無効にします。 環境で拡張機能を有効にして展開するには、「管理する設定」を参照してください。 

#### <a name="extension-installation-blocklist"></a>拡張機能のインストール blocklist
**既定値:** すべての

Microsoft Managed Desktop は、このポリシーを設定して、管理されたエンドポイントに Chrome 拡張機能がインストールされないようにします。 Chromium 拡張モデルには、データ損失防止、プライバシー、およびデバイスを侵害する可能性があるその他のリスクを含む、既知の risksassociated があります。 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>ユーザーレベルのネイティブメッセージングホストを許可する (管理者権限なしでインストールされる)

**既定値:** 党

このポリシーを無効にすると、Microsoft Edge はシステムレベルでインストールされているネイティブメッセージングホストのみを使用します。 ネイティブメッセージングホストは、Chrome 拡張機能の一部であり、ブラウザーはユーザーのエンドポイントの他の部分と対話し、さまざまなセキュリティ上の問題を作成できます。  

### <a name="secure-sockets-layer-ssl"></a>Secure Sockets Layer (SSL)

#### <a name="minimum-ssl-version"></a>最小 SSL バージョン

**既定値:** サポートされる最低限の TLS 1.2

安全性の低い TLS 1.1 を使用する場合は、これを要求できます。

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>ユーザーが SSL の警告ページから先に進むことができるようにする

**既定値:** 党

SSL エラーが発生しているサイトにユーザーがアクセスできるようにするため、この設定を有効にすることはお勧めしません。

### <a name="microsoft-defender-smart-screen"></a>Microsoft Defender Smart 画面

#### <a name="configure-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen を構成する

**既定値:** い

エンドユーザーを保護するために、既定で有効になっています。

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>サイトの Microsoft Defender SmartScreen プロンプト

**既定値:** い

この設定を無効にすることをお勧めします。これにより、ユーザーは警告を無視し、潜在的な悪意のあるサイトに進むことができるようになります。

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>ダウンロードに関する Microsoft Defender SmartScreen の警告をバイパスできないようにする

**既定値:** い

この設定を無効にして、ユーザーが警告を無視し、検証されていないダウンロードを完了できるようにすることをお勧めしません。

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>既定の Adobe Flash 設定

**既定値:** 党

関連するセキュリティリスクがあるため、Flash の使用はお勧めしません。 フラッシュに依存するプロセスがまだある場合は、 **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ポリシーを設定して、必要なサイトでフラッシュを有効にします。 許可されているサイトのリストを保持してフラッシュを使用できない場合は、変更要求を開始して、 **[再生する]** の値を変更します。これにより、ユーザーはフラッシュを実行する必要がある場合に選択できるようになります。

### <a name="password-manager"></a>パスワードマネージャー

#### <a name="enable-saving-passwords-to-the-password-manager"></a>パスワードをパスワードマネージャーに保存できるようにする

**既定値:** 党

エンドユーザーが自分のデバイスにパスワードを保存することを許可することはお勧めしません。

### <a name="other-settings"></a>その他の設定

#### <a name="enable-site-isolation-for-every-site"></a>サイトごとにサイト分離を有効にする

**既定値:** い

このポリシーが有効になっている場合、ユーザーは、各サイトが独自のプロセスで実行される既定の動作をオプトアウトできません。

#### <a name="supported-authentication-schemes"></a>サポートされる認証スキーム

**既定値:** NTLM、ネゴシエート

Microsoft マネージドデスクトップは、基本認証スキームまたはダイジェスト認証スキームをサポートしていません。

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>初回実行時に別のブラウザーのデータと設定を自動的にインポートする

**既定値:** サポートされているすべてのデータ型と設定を既定のブラウザーから自動的にインポートする 

このポリシーを適用すると、最初の実行環境で [インポート] セクションがスキップされ、ユーザーの操作が最小限になります。 以前のバージョンの Microsoft Edge のブラウザーデータは、この設定に関係なく、常に最初の実行時に自動的に移行されます。 


## <a name="settings-you-manage"></a>管理する設定

Microsoft Intune の管理用テンプレートプロファイルを使用していないマイクロ Sft エッジ設定を展開することができます。 詳細については、「microsoft [Edge ポリシー設定を Microsoft Intune で構成する](https://docs.microsoft.com/deployedge/configure-edge-with-intune)」を参照してください。 Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune で Windows 10 デバイスのカスタム設定を使用できます。

### <a name="enabling-specific-chrome-extensions"></a>特定の Chrome 拡張機能を有効にする

管理用テンプレートは、Microsoft Intune に特定の Chrome 拡張機能を展開するための設定を提供します。 **Microsoft Edge > 拡張機能を使用して、特定の拡張機能をインストール >** ことができます >、[コンピューターの構成] で見つけることができます。

### <a name="install-extensions-silently"></a>拡張機能をサイレントインストールする

管理用テンプレートを使用して Microsoft Edge を設定し、ユーザーに通知せずに拡張機能をインストールすることもできます。 **Microsoft Edge > 拡張 > 機能を使用して、サイレントモードでインストールされる拡張機能を制御する >**、[コンピューターの構成の詳細について説明します。

### <a name="other-common-enterprise-policies"></a>その他の一般的なエンタープライズポリシー

Microsoft Edge では、非常に多くの追加ポリシーが提供されています。 一般的なもののいくつかを次に示します。
 
- [エンタープライズサイトリストと IE モードのサイトを構成する](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [スタートアップ、ホームページ、および新しいタブページの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [サーフィンゲームの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [プロキシサーバーの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

