---
title: 新しい Microsoft Edge
description: 新しいエッジ ブラウザーの展開および更新方法について説明します。
keywords: browser, Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 033826a7f82278f6e36b422284a1076cba57d584
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921980"
---
# <a name="new-microsoft-edge-app"></a>新しい Microsoft Edge アプリ

新しい [Microsoft Edge ブラウザーは](https://www.microsoft.com/edge) 、閲覧中にプライバシーの向上、生産性の向上、価値の向上を実現する、世界クラスのパフォーマンスを提供します。 Microsoft Managed Desktop は、環境内の新しいエッジ ブラウザーの展開のパブリック プレビューを提供しています。

## <a name="initial-deployment"></a>初期展開

Microsoft Managed Desktop デバイスを新しい Microsoft Edge ブラウザーに移行するには、Microsoft 管理デスクトップ ポータルから IT サポート チケットをファイルします。 チケットをファイルするときにエッジ安定チャネルをテスト グループに展開し、24 時間ごとに後続の各展開グループに展開します。 展開を一時停止するには、Operations に保留を求める別のチケットをファイルします。

ベータ [チャネルは、](/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証のために要求に応じて利用することもできます。 Microsoft Managed Desktop は、必要に応じてアプリケーションをテスト グループとファースト グループに展開し、それらのユーザー全員が安定チャネルに加えてベータ チャネルを持つ状態になります。 ベータ チャネルへのアクセスが必要な他のユーザーの場合は、それらをモダン ワークプレース **- エッジ ベータ** ユーザー グループに追加し、ポータル サイトからインストールします。

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge の更新プログラム

Microsoft Managed Desktop[](/deployedge/microsoft-edge-channels#stable-channel)は、約 6 週間ごとに自動更新される Microsoft Edge の Stable チャネルを展開します。 Stable チャネルの更新プログラムは、[](/deployedge/microsoft-edge-update-progressive-rollout)お客様に最適なエクスペリエンスを確保するために、Microsoft Edge 製品グループによって段階的に展開されます。 

ベータ [チャネルは、](/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証のために Test グループと First グループの両方のデバイスに展開されます。 このチャネルは完全にサポートされ、約 6 週間ごとに新機能が自動更新されます。

Microsoft Edge が正しく更新されるようにするには、Microsoft Edge 更新ポリシーを [変更しません](/deployedge/microsoft-edge-update-policies)。



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop によって管理される設定

Microsoft Managed Desktop は、ブラウザーをセキュリティで保護するための Microsoft Edge の既定のポリシー セットを作成しました。 既定のブラウザー設定は次のとおりです。

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 拡張機能

Microsoft Managed Desktop デバイス上の Microsoft Edge のセキュリティ基準は、すべての Chrome 拡張機能を無効にし、ユーザーをセキュリティで保護するための 2 つのポリシーを設定します。 環境で拡張機能を有効にして展開するには、「管理する設定」を参照してください。 

#### <a name="extension-installation-blocklist"></a>拡張機能のインストール ブロックリスト
**既定値:** すべての

Microsoft Managed Desktop は、Chrome 拡張機能が管理エンドポイントにインストールされるのを防ぐために、このポリシーを設定します。 データ損失の保護、プライバシー、デバイスを侵害する可能性のあるその他のリスクなど、クロム拡張機能モデルに関連する既知のリスクがあります。 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>ユーザー レベルのネイティブ メッセージング ホストを許可する (管理者のアクセス許可なしでインストール)

**既定値:** 無効

このポリシーを無効にすると、Microsoft Edge はシステム レベルにインストールされているネイティブ メッセージング ホストのみを使用します。 ネイティブ メッセージング ホストは Chrome 拡張機能の一部で、ブラウザーがユーザーのエンドポイントの他の部分と対話し、さまざまなセキュリティ上の懸念を生み出します。  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>TLS の最小バージョン

**既定値:** サポートされる最小 TLS 1.2

安全性の低い TLS 1.1 を使用する場合は、要求を送信できます。

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>ユーザーが SSL 警告ページから進むのを許可する

**既定値:** 無効

ユーザーが TSL エラーのあるサイトにアクセスできるので、この設定を有効にすることをお勧めしません。

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>SmartScreen Windows Defender構成する

**既定値:** 有効

ユーザーの保護に役立つ既定で有効になっています。

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defenderの SmartScreen プロンプト

**既定値:** 有効

この設定を無効にしても、ユーザーは警告を無視し、悪意のある可能性のあるサイトを引き続き使用できます。

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>ダウンロードに関する SmartScreen Windows Defenderのバイパスを防止する

**既定値:** 有効

ユーザーが警告を無視して未確認のダウンロードを完了できるので、この設定を無効にすることをお勧めしません。

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Adobe Flash の既定の設定

**既定値:** 無効

関連付けられたセキュリティ リスクのため、Flash の使用はお勧めしません。 Flash に依存するプロセスがまだ存在する場合は **[、PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ポリシーを設定して、必要なサイトで Flash を有効にしてください。 Flash を使用するサイトの許可リストを維持できない場合は、変更要求を送信して値を [Click **to Play]** に変更します。これにより、ユーザーは Flash の実行が適切なときに選択できます。

### <a name="password-manager"></a>パスワード マネージャー

#### <a name="enable-saving-passwords-to-the-password-manager"></a>パスワード マネージャーへのパスワードの保存を有効にする

**既定値:** 無効

ユーザーが自分のデバイスにパスワードを保存することを許可はお勧めしません。

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorerエッジのモード
Microsoft Edge で IE モードを利用すると、組織が必要とするすべてのサイトを 1 つのブラウザーで簡単に使用できます。 このエンジンは、クロム レンダリング エンジンと互換性のあるサイトに統合クロム エンジンを使用し、IE 機能に依存しないサイトや依存関係を持つサイトには、Internet Explorer 11 (IE11) の Trident MSHTML エンジンを使用します。 [詳細](https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop では、既定Internet Explorerデバイスのモードを有効にします。 

#### <a name="internet-explorer-mode-integration"></a>Internet Explorerモードの統合
**既定値:** Internet Explorerモード

既定では、デバイスは Internet Explorer モードを使用Internet Explorer設定できます。 この動作を変更するには、サポート要求を送信します。

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>[エンタープライズ モード サイト] リストにサイトを追加する
サイトを[エンタープライズ サイト] Internet Explorer開く場合は、[エンタープライズ サイト] リストにサイトを [含める必要があります](/DeployEdge/edge-ie-mode-sitelist)。 エンタープライズ サイトリストの保守と展開は、お客様の責任です。 詳細については、「Configure [using the Configure using Enterprise Mode Site List policy」を参照してください。](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>その他の設定

#### <a name="enable-site-isolation-for-every-site"></a>すべてのサイトでサイトの分離を有効にする

**既定値:** 有効

このポリシーを有効にすると、ユーザーは、各サイトが独自のプロセスで実行される既定の動作をオプトアウトできません。

#### <a name="supported-authentication-schemes"></a>サポートされている認証スキーム

**既定値:** NTLM、ネゴシエート

Microsoft Managed Desktop では、基本認証またはダイジェスト認証スキームはサポートされていません。

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>最初の実行時に別のブラウザーのデータと設定を自動的にインポートする

**既定値:** サポートされているすべてのデータ型と設定を既定のブラウザーから自動的にインポートする 

このポリシーを適用すると、最初の実行エクスペリエンスはインポート セクションをスキップし、ユーザーの操作を最小限に抑える。 Microsoft Edge の古いバージョンのブラウザー データは、この設定に関係なく、最初の実行時に常にサイレント モードで移行されます。 


## <a name="settings-you-manage"></a>管理する設定

Microsoft Intune の管理用テンプレート プロファイルを使用して、前に説明していない Microsoft Edge 設定を展開できます。 詳細については [、「Microsoft Intune で Microsoft Edge ポリシー設定を構成する」を参照してください](/deployedge/configure-edge-with-intune)。 Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune で Windows 10 デバイスのカスタム設定を使用できます。

### <a name="enabling-specific-chrome-extensions"></a>特定の Chrome 拡張機能を有効にする

管理用テンプレートには、Microsoft Intune を使用して特定の Chrome 拡張機能を展開する設定が用意されています。 このファイルは **、「Microsoft Edge >拡張機能>特定>を** 許可する」で確認できます。

### <a name="install-extensions-silently"></a>拡張機能をサイレント インストールする

管理用テンプレートを使用して、ユーザーに通知せずに拡張機能をインストールするように Microsoft Edge を設定することもできます。 それを見つけることができます コンピューター構成 Microsoft Edge > >拡張機能>をサイレント モード **でインストールします**。

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge の更新ポリシー
Microsoft Edge が正しく更新されるようにするには、Microsoft Edge 更新ポリシーを [変更しません](/deployedge/microsoft-edge-update-policies)。

### <a name="other-common-enterprise-policies"></a>その他の一般的なエンタープライズ ポリシー

Microsoft Edge は、他にも多くのポリシーを提供しています。 以下に、より一般的な例を示します。
 
- [エンタープライズ サイト一覧と IE モードでサイトを構成する](/deployedge/edge-ie-mode-sitelist)
- [起動、ホーム ページ、および新しいタブ ページの設定を構成する](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [サーフ ゲームの設定を構成する](/deployedge/microsoft-edge-policies#allowsurfgame)
- [プロキシ サーバーの設定を構成する](/deployedge/microsoft-edge-policies#proxy-server)