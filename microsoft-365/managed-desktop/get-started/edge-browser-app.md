---
title: 新しい Microsoft Edge
description: 新しいエッジ ブラウザーの展開方法と更新方法について説明します。
keywords: ブラウザー, Microsoft マネージド デスクトップ, Microsoft 365, サービス, ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841341"
---
# <a name="new-microsoft-edge-app"></a>新しい Microsoft Edge アプリ

新しい [Microsoft Edge ブラウザーは](https://www.microsoft.com/edge) 、閲覧中のプライバシーの向上、生産性の向上、価値の向上により、世界クラスのパフォーマンスを提供します。 Microsoft マネージド デスクトップは、環境内での新しい Edge ブラウザーの展開のパブリック プレビューを提供しています。

## <a name="initial-deployment"></a>初期展開

Microsoft マネージド デスクトップ デバイスを新しい Microsoft Edge ブラウザーに移行するには、Microsoft マネージド デスクトップ ポータルから IT サポート チケットを作成します。 チケットをファイルするときに Edge Stable チャネルをテスト グループに展開し、24 時間ごとに後続の各展開グループに展開します。 展開を一時停止するには、Operations に保留を求める別のチケットを作成します。

Beta [チャネルは、](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証を要求された場合にも利用できます。 Microsoft マネージド デスクトップは、必要に応じてアプリケーションをテスト グループと最初のグループに展開し、これらのユーザー全員が Stable チャネルに加えてベータ チャネルを利用できます。 ベータ チャネルにアクセスする必要がある他のユーザーの場合は、そのユーザーを **モダン Workplace - Edge Beta Users** グループに追加し、ポータル サイトからインストールします。

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge の更新

Microsoft マネージド デスクトップは、約 6 週間ごとに自動更新される Microsoft Edge の [Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) チャネルを展開します。 Stable チャネルの更新プログラムは、[](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout)お客様に最適なエクスペリエンスを保証するために、Microsoft Edge 製品グループによって段階的に展開されます。 

Beta [チャネルは、](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証のために Test グループと First グループの両方のデバイスに展開されます。 このチャネルは完全にサポートされ、約 6 週間ごとに新機能で自動更新されます。

Microsoft Edge が正しく更新されるようにするには、Microsoft Edge の更新ポリシーを [変更しません](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップで管理される設定

Microsoft マネージド デスクトップでは、ブラウザーをセキュリティで保護するための Microsoft Edge の既定のポリシー セットが作成されています。 既定のブラウザー設定は次のとおりです。

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 拡張機能

Microsoft マネージド デスクトップ デバイス上の Microsoft Edge のセキュリティ基本計画では、すべての Chrome 拡張機能を無効にし、ユーザーをセキュリティで保護する 2 つのポリシーを設定します。 環境で拡張機能を有効にして展開するには、「管理する設定」を参照してください。 

#### <a name="extension-installation-blocklist"></a>拡張機能のインストールのブロックリスト
**既定値:** すべての

Microsoft マネージド デスクトップでは、Chrome 拡張機能が管理エンドポイントにインストールされるのを防ぐために、このポリシーが設定されています。 Chromium 拡張機能モデルには、データ損失防止、プライバシー、デバイスを侵害する可能性のあるその他のリスクなど、既知のリスクがあります。 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>ユーザー レベルのネイティブ メッセージング ホストを許可する (管理者のアクセス許可なしでインストールされる)

**既定値:** 無効

このポリシーを無効にすると、Microsoft Edge はシステム レベルにインストールされているネイティブ メッセージング ホストのみを使用します。 ネイティブ メッセージング ホストは Chrome 拡張機能の一部で、ブラウザーがユーザーのエンドポイントの他の部分と対話し、さまざまなセキュリティ上の問題を引き起こす可能性があります。  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>TLS の最小バージョン

**既定値:** サポートされる TLS 1.2 以上

セキュリティが低い TLS 1.1 を使用する場合は、要求を送信できます。

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>ユーザーが SSL 警告ページから続行できます。

**既定値:** 無効

この設定を有効にすると、ユーザーは TSL エラーが発生したサイトにアクセスできます。

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>SmartScreen Windows Defender構成する

**既定値:** 有効

ユーザーを保護するために既定で有効になっています。

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen プロンプトを表示する

**既定値:** 有効

この設定を無効にすることで、ユーザーは警告を無視し、悪意のある可能性のあるサイトを引き続き使用できます。

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>ダウンロードに関する SmartScreen Windows Defenderのバイパスを回避する

**既定値:** 有効

この設定を無効にすることで、ユーザーは警告を無視して未確認のダウンロードを完了できます。

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Adobe Flash の既定の設定

**既定値:** 無効

関連するセキュリティ リスクのため、Flash の使用はお勧めしません。 Flash に依存するプロセスがまだ存在する場合は **[、PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ポリシーを設定して、必要なサイトで Flash を有効にしてください。 Flash を使用するサイトの許可リストを保持できない場合は、変更要求を送信して値を Click **to Play** に変更します。これにより、ユーザーは Flash を実行する適切なときに選択できます。

### <a name="password-manager"></a>パスワード マネージャー

#### <a name="enable-saving-passwords-to-the-password-manager"></a>パスワード マネージャーへのパスワードの保存を有効にする

**既定値:** 無効

ユーザーがデバイスにパスワードを保存することを許可はお勧めしません。

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Microsoft Edge Internet Explorerモード
Microsoft Edge で IE モードを利用すると、組織が必要とするすべてのサイトを 1 つのブラウザーで簡単に使用できます。 Chromium レンダリング エンジンと互換性のあるサイトには統合 Chromium エンジンを使用し、IE の機能に依存していないサイトや IE 機能に依存しないサイトには Internet Explorer 11 (IE11) の Trident MSHTML エンジンを使用します。 [詳細](https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft マネージド デスクトップでは、デバイスInternet Explorerモードが既定で有効になります。 

#### <a name="internet-explorer-mode-integration"></a>Internet Explorerモードの統合
**既定値:** Internet Explorer モード

既定では、デバイスは Internet Explorer モードを使用する設定になっていますが、代わりにスタンドアロンの Internet Explorer 11 ウィンドウでサイトを開Internet Explorer設定できます。 この動作を変更するには、サポート要求を送信します。

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>エンタープライズ モード サイト一覧にサイトを追加する
サイトをエンタープライズ サイト 一Internet Explorerモードで開く場合は、それらをエンタープライズ サイト一覧に [含める必要があります](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)。 エンタープライズ サイト一覧の保守と展開は、お客様の責任において行います。 詳細については、「エンタープライズ モード サイト [一覧の構成」ポリシーを使用した構成に関するページを参照してください。](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>その他の設定

#### <a name="enable-site-isolation-for-every-site"></a>すべてのサイトでサイトの分離を有効にする

**既定値:** 有効

このポリシーを有効にすると、ユーザーは各サイトが独自のプロセスで実行される既定の動作を無効にすることはできません。

#### <a name="supported-authentication-schemes"></a>サポートされる認証スキーム

**既定値:** NTLM、ネゴシエート

Microsoft マネージド デスクトップでは、基本認証スキームまたはダイジェスト認証スキームはサポートされていません。

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>最初の実行時に別のブラウザーのデータと設定を自動的にインポートする

**既定値:** サポートされているデータ型と設定を既定のブラウザーから自動的にインポートする 

このポリシーが適用されると、最初の実行エクスペリエンスはインポート セクションをスキップし、ユーザーの操作を最小限に抑える必要があります。 以前のバージョンの Microsoft Edge のブラウザー データは、この設定に関係なく、最初の実行時に常に自動的に移行されます。 


## <a name="settings-you-manage"></a>管理する設定

Microsoft Intune の管理用テンプレート プロファイルを使用して、前に説明した Microsoft Edge の設定を展開できます。 詳細については [、「Microsoft Intune で Microsoft Edge ポリシー設定を構成する」を参照してください](https://docs.microsoft.com/deployedge/configure-edge-with-intune)。 Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune で Windows 10 デバイスのカスタム設定を使用できます。

### <a name="enabling-specific-chrome-extensions"></a>特定の Chrome 拡張機能を有効にする

管理用テンプレートには、Microsoft Intune で特定の Chrome 拡張機能を展開する設定が用意されています。 この機能は、Microsoft Edge の [コンピューターの構成] **>[>拡張機能**] >特定の拡張機能のインストールを許可する] にあります。

### <a name="install-extensions-silently"></a>拡張機能をサイレント インストールする

管理用テンプレートを使用して、ユーザーに警告せずに拡張機能をインストールするように Microsoft Edge を設定することもできます。 [コンピューターの構成] > Microsoft Edge >拡張機能>サイレント インストールされる拡張機能 **を制御します**。

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge 更新ポリシー
Microsoft Edge が正しく更新されるようにするには、Microsoft Edge の更新ポリシーを [変更しません](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)。

### <a name="other-common-enterprise-policies"></a>その他の一般的なエンタープライズ ポリシー

Microsoft Edge には、他にも多くのポリシーが用意されています。 以下に、より一般的な機能の一部を示します。
 
- [エンタープライズ サイト一覧と IE モードでサイトを構成する](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [起動、ホーム ページ、および新しいタブ ページの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [ゲームの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [プロキシ サーバーの設定を構成する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

