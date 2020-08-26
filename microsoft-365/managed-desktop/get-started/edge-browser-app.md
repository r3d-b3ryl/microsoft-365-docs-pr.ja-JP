---
title: 新しい Microsoft Edge
description: ''
keywords: ブラウザー、Microsoft Managed Desktop、Microsoft 365、service、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 089d9dc79da568a43c1d5701d7bc52d9bed0f4f5
ms.sourcegitcommit: c76c025fe75cd9c06eccbf9c7fc887b09da36659
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903873"
---
# <a name="new-microsoft-edge-app"></a>新しい Microsoft Edge アプリ

新しい [Microsoft Edge ブラウザー](https://www.microsoft.com/edge) は、閲覧時に、プライバシー、生産性、および価値の高い世界クラスのパフォーマンスを提供します。 Microsoft マネージドデスクトップは、お客様の環境に新しいエッジブラウザーを展開するためのパブリックプレビューを提供しています。

## <a name="initial-deployment"></a>初期展開

Microsoft マネージドデスクトップデバイスを新しい Microsoft Edge ブラウザーに移行するには、Microsoft マネージドデスクトップポータルを使用して、IT サポートチケットをファイルに追加します。 チケットをファイル化した後、24時間ごとに展開グループに展開すると、エッジ安定チャネルがテストグループに展開されます。 展開を一時停止するには、別のチケットをファイルに保存する操作を要求します。

また、 [ベータチャネル](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) は、組織内の代表的な検証の要求時に使用することもできます。 Microsoft マネージドデスクトップは、必要に応じて、アプリケーションをテストおよび最初のグループに展開します。これにより、これらのすべてのユーザーは、安定したチャネルに加えて、ベータチャネルを利用できるようになります。 ベータチャネルにアクセスする必要がある追加のユーザーについては、 **最新の Workplace Edge ベータユーザー** グループに追加して、会社のポータルからインストールする必要があります。

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge への更新

Microsoft マネージドデスクトップは、6週間ごとに自動更新される、Microsoft Edge の安定した [チャネル](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) を展開します。 お客様に最適な環境を実現するために、安定したチャネルでの更新は、Microsoft Edge 製品グループによって [段階的](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) にロールアウトされています。 

[ベータチャネル](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel)は、組織内の代表的な検証のためにテストと最初のグループの両方のデバイスに展開されます。 このチャネルは完全にサポートされており、約6週間ごとに新機能によって自動更新されます。

Microsoft Edge が正しく更新されるように、Microsoft Edge [更新ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)を変更しないでください。

### <a name="microsoft-edge-beta-channel"></a>Microsoft Edge ベータチャネル


## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップによって管理される設定

Microsoft マネージドデスクトップでは、ブラウザーをセキュリティで保護するために、Microsoft Edge の既定のポリシーセットが作成されています。 既定のブラウザーの設定は次のとおりです。

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 拡張機能

Microsoft マネージドデスクトップデバイス上の Microsoft Edge のセキュリティベースラインは、2つのポリシーを設定して、Chrome 拡張およびセキュリティで保護されたエンドユーザーをすべて無効にします。 環境で拡張機能を有効にして展開するには、「管理する設定」を参照してください。 

#### <a name="extension-installation-blocklist"></a>拡張機能のインストール blocklist
**既定値:** すべての

Microsoft Managed Desktop は、このポリシーを設定して、管理されたエンドポイントに Chrome 拡張機能がインストールされないようにします。 Chromium 拡張モデルに関連する既知のリスクには、データ損失防止、プライバシー、およびデバイスを侵害する可能性があるその他のリスクが含まれます。 

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

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Windows Defender SmartScreen を構成する

**既定値:** い

エンドユーザーを保護するために、既定で有効になっています。

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>サイトの Windows Defender SmartScreen プロンプト

**既定値:** い

この設定を無効にすることをお勧めします。これにより、ユーザーは警告を無視し、潜在的な悪意のあるサイトに進むことができるようになります。

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>ダウンロードに関する Windows Defender SmartScreen の警告をバイパスできないようにする

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

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Microsoft Edge の Internet Explorer モード
Microsoft Edge で IE モードを使用すると、組織が必要とするすべてのサイトを1つのブラウザーで簡単に使用できるようになります。 Chromium レンダリングエンジンと互換性のあるサイトには、統合された Chromium エンジンを使用します。また、IE 機能に依存していないサイトまたは Internet Explorer 11 (IE11) の Trident MSHTML エンジンを使用します。 [詳細情報](https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft マネージドデスクトップでは、既定でデバイスの Internet Explorer モードが有効になっています。 

#### <a name="internet-explorer-mode-integration"></a>Internet Explorer モードの統合
**既定値:** Internet Explorer モード

既定では、デバイスは Internet Explorer モードを使用するように設定されていますが、代わりにスタンドアロンの Internet Explorer 11 ウィンドウでサイトを開くように設定することもできます。 これを変更するには、サポート要求をファイルにします。

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>エンタープライズモードのサイトリストにサイトを追加する
サイトを Internet Explorer モードで開くには、それらを [エンタープライズサイトリスト](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)に含める必要があります。 エンタープライズサイトリストの管理と展開は責任を負っています。 詳細については、「configure [Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy) 」を参照してください。

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

Microsoft Intune の管理用テンプレートプロファイルを使用していない Microsoft Edge の設定を展開することができます。 詳細については、「microsoft [Edge ポリシー設定を Microsoft Intune で構成する](https://docs.microsoft.com/deployedge/configure-edge-with-intune)」を参照してください。 Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune で Windows 10 デバイスのカスタム設定を使用できます。

### <a name="enabling-specific-chrome-extensions"></a>特定の Chrome 拡張機能を有効にする

管理用テンプレートは、Microsoft Intune に特定の Chrome 拡張機能を展開するための設定を提供します。 **Microsoft Edge > 拡張機能を使用して、特定の拡張機能をインストール >** ことができます >、[コンピューターの構成] で見つけることができます。

### <a name="install-extensions-silently"></a>拡張機能をサイレントインストールする

管理用テンプレートを使用して Microsoft Edge を設定し、ユーザーに通知せずに拡張機能をインストールすることもできます。 **Microsoft Edge > 拡張 > 機能を使用して、サイレントモードでインストールされる拡張機能を制御する >**、[コンピューターの構成の詳細について説明します。

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge 更新ポリシー
Microsoft Edge が正しく更新されるように、Microsoft Edge [更新ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)を変更しないでください。

### <a name="other-common-enterprise-policies"></a>その他の一般的なエンタープライズポリシー

Microsoft Edge では、非常に多くの追加ポリシーが提供されています。 一般的なもののいくつかを次に示します。
 
- [エンタープライズサイトリストと IE モードのサイトを構成する](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [スタートアップ、ホームページ、および新しいタブページの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [サーフィンゲームの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [プロキシサーバーの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

