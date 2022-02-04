---
title: 新しい Microsoft Edge
description: 新しいブラウザーを展開Microsoft Edge更新する方法について説明します。
keywords: 'ブラウザー, Microsoft Managed Desktop, Microsoft 365, サービス, ドキュメント'
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
---


# <a name="new-microsoft-edge-app"></a>新Microsoft Edgeアプリ

新しい[Microsoft Edgeブラウザーは](https://www.microsoft.com/edge)、閲覧中にプライバシーの向上、生産性の向上、価値の向上を実現する、世界クラスのパフォーマンスを提供します。 Microsoft Managed Desktop では、環境内の新しいブラウザーの展開Microsoft Edgeプレビューを提供しています。

## <a name="initial-deployment"></a>初期展開

Microsoft Managed Desktop デバイスを新しい Microsoft Edge ブラウザーに移行するには、Microsoft 管理デスクトップ ポータルから IT サポート チケットをファイルします。

チケットをファイルするときに、Microsoft Edge Stable チャネルをテスト グループに展開します。 次に、24 時間ごとに、後続の各展開グループに展開します。 展開を一時停止するには、Operations に保留を求める別のチケットをファイルします。

ベータ [チャネルは、](/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証のために要求に応じて利用することもできます。 Microsoft Managed Desktop は、必要に応じてアプリケーションをテスト グループとファースト グループに展開し、それらのユーザー全員が安定チャネルに加えてベータ チャネルを持つ状態になります。 ベータ チャネルへのアクセスが必要な他のユーザーの場合は、それらをモダン ワークプレース **-** エッジ ベータ ユーザー グループに追加し、そのユーザーにベータ版のサイトからインストールポータル サイト

## <a name="updates-to-microsoft-edge"></a>ユーザーの更新Microsoft Edge

Microsoft Managed Desktop は、6 週間[](/deployedge/microsoft-edge-channels#stable-channel)ごとに自動的に更新Microsoft Edgeの Stable チャネルを展開します。 Stable チャネルの更新プログラムは、顧客[](/deployedge/microsoft-edge-update-progressive-rollout)に最適なエクスペリエンスを確保Microsoft Edge製品グループによって段階的に展開されます。

ベータ [チャネルは、](/deployedge/microsoft-edge-channels#beta-channel) 組織内の代表的な検証のために Test グループと First グループの両方のデバイスに展開されます。 このチャネルは、約 6 週間ごとに完全にサポートされ、新しい機能で自動的に更新されます。

> [!IMPORTANT]
> 更新プログラムがMicrosoft Edge確認するには、更新ポリシーを変更Microsoft Edge[しません](/deployedge/microsoft-edge-update-policies)。

## <a name="settings-managed-by-microsoft-managed-desktop"></a>設定によって管理される Microsoft Managed Desktop

Microsoft Managed Desktop では、ブラウザーをセキュリティで保護するために、Microsoft Edgeポリシーのセットを作成しました。 既定のブラウザー設定は次のとおりです。

### <a name="microsoft-edge-extensions"></a>Microsoft Edge拡張機能

Microsoft Managed Desktop デバイスMicrosoft Edgeセキュリティベースラインは、すべての Chrome 拡張機能を無効にし、ユーザーをセキュリティで保護するための 2 つのポリシーを設定します。 環境で拡張機能を有効にして展開するには、「管理する設定[」を参照してください](#settings-you-manage)。

| Setting | 既定値 | 説明 |
| ------ | ------ | ------ |
| 拡張機能のインストール ブロックリスト | すべて | Microsoft Managed Desktop は、Chrome 拡張機能が管理エンドポイントにインストールされるのを防ぐために、このポリシーを設定します。 データ損失の保護、プライバシー、およびデバイスを侵害する可能性のあるその他のリスクなど、Chromium拡張機能モデルに関連する既知のリスクがあります。 |
| ユーザー レベルのネイティブ メッセージング ホストを許可する (管理者のアクセス許可なしでインストール) | 無効 | このポリシーを無効にすると、Microsoft Edgeシステム レベルにインストールされているネイティブ メッセージング ホストだけが使用されます。 ネイティブ メッセージング ホストは Chrome 拡張機能の一部で、ブラウザーがユーザーのエンドポイントの他の部分と対話し、さまざまなセキュリティ上の問題を引き起こす可能性があります。 |

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

| Setting | 既定値 | 説明
| ------ | ------ | ------ |
| TLS の最小バージョン | サポートされる最小 TLS 1.2 | 安全性の低い TLS 1.1 を使用する場合は、要求を送信できます。 |
| ユーザーが SSL 警告ページから進むのを許可する | 無効 | ユーザーが TSL エラーのあるサイトにアクセスできるので、この設定を有効にすることをお勧めしません。 |

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

| Setting | 既定値 | 説明
| ------ | ------ | ------ |
| SmartScreen Windows Defender構成する | Enabled | ユーザーの保護に役立つ既定で有効になっています。 |
| Windows Defenderの SmartScreen プロンプトの表示 | Enabled | この設定を無効にしても、ユーザーは警告を無視し、悪意のあるサイトを引き続き使用できます。 |
| ダウンロードに関する SmartScreen Windows Defenderのバイパスを防止する | Enabled | ユーザーが警告を無視して未確認のダウンロードを完了できるので、この設定を無効にすることをお勧めしません。 |

### <a name="adobe-flash"></a>Adobe Flash

| Setting | 既定値 | 説明
| ------ | ------ | ------ |
| Adobe Flash の既定の設定 | 無効 | 関連付けられたセキュリティ リスクのため、Flash の使用はお勧めしません。 <br><br> Flash に依存するプロセスがまだ存在する場合は、 **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ポリシーを設定して、必要なサイトで Flash を有効にしてください。 Flash を使用するサイトの許可リストを維持できない場合は、変更要求を送信して値を [Click **to Play**] に変更します。これにより、ユーザーは Flash の実行が適切なときに選択できます。 |

### <a name="password-manager"></a>パスワード マネージャー

| Setting | 既定値 | 説明
| ------ | ------ | ------ |
| パスワード マネージャーへのパスワードの保存を有効にする | 無効 | パスワード マネージャーは既定で無効になっています。 この機能を有効にする場合は、サポート要求を送信し、サービス エンジニアが環境内で設定を有効にできます。 |

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer モード (Microsoft Edge

Microsoft Edge で IE モードを利用すると、組織が必要とするすべてのサイトを 1 つのブラウザーで簡単に使用できます。 この機能は、Chromiumレンダリング エンジンと互換性のあるサイトに統合Chromium使用します。 Microsoft Edgeは、IE 機能に依存していない、または依存関係を持つサイトに対して、Internet Explorer 11 (IE11) の Trident MSHTML エンジンを使用します。 [詳細情報](/DeployEdge/edge-ie-mode)

Microsoft Managed Desktop では、既定Internet Explorerデバイスの管理モードが有効になります。

| Setting | 既定値 | 説明
| ------ | ------ | ------ |
| Internet Explorerモードの統合 | Internet Explorer モード | 既定では、デバイスは Internet Explorer モードを使用Internet Explorer設定できます。 この動作を変更するには、サポート要求を送信します。 |
| サイトを Enterprise モード サイト一覧に追加する | 説明を参照してください。 | サイトをサイト モードでInternet Explorerするには、[サイト] リストにサイトをEnterprise[する必要があります](/DeployEdge/edge-ie-mode-sitelist)。 サイト一覧のEnterprise展開は、お客様の責任です。 詳細については、「Configure [using the Configure using the Configure using the Configure Enterprise モード サイト リスト ポリシー」を参照してください](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)。 |

### <a name="other-settings"></a>その他の設定

| Setting | 既定値 | 説明
| ------ | ------ | ------ |
| すべてのサイトでサイトの分離を有効にする | Enabled | このポリシーを有効にすると、ユーザーは、各サイトが独自のプロセスで実行される既定の動作をオプトアウトできません。 |
| サポートされている認証スキーム | NTLM、ネゴシエート | Microsoft Managed Desktop では、基本認証またはダイジェスト認証スキームはサポートされていません。 |
| 最初の実行時に別のブラウザーのデータと設定を自動的にインポートする | サポートされているすべてのデータ型と設定を既定のブラウザーから自動的にインポートします。 | このポリシーを適用すると、最初の実行エクスペリエンスはインポート セクションをスキップし、ユーザーの操作を最小限に抑える。 この設定に関係なく、Microsoft Edgeの古いバージョンのブラウザー データは、最初の実行時に常にサイレント モードで移行されます。 |

## <a name="settings-you-manage"></a>設定管理する方法

[管理用テンプレート] プロファイルMicrosoft Edge使用して、前に説明していない任意の設定を展開Microsoft Intune。 詳細については、「Configure [Microsoft Edge ポリシー設定」を参照Microsoft Intune](/deployedge/configure-edge-with-intune)。 Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune の Windows 10 デバイスのカスタム設定を使用できます。

| Setting | 説明
| ------ | ------ |
| 特定の Chrome 拡張機能を有効にする | 管理用テンプレートには、特定の Chrome 拡張機能を展開する設定が用意Microsoft Intune。 [コンピューターの構成] [**拡張機能] > Microsoft Edge >[>特定の拡張機能のインストールを許可する] で確認できます**。 |
| 拡張機能をサイレント インストールする | 管理用テンプレートを使用して、ユーザーにMicrosoft Edge拡張機能をインストールするように設定することもできます。 [コンピューターの構成] [拡張機能] > Microsoft Edge >[>にインストールされている **拡張機能を制御する] で確認できます**。 |
| Microsoft Edge更新ポリシー | 更新プログラムがMicrosoft Edge確認するには、更新ポリシーを変更Microsoft Edge[しません](/deployedge/microsoft-edge-update-policies)。 |
| その他の一般的なエンタープライズ ポリシー | Microsoft Edge多くの他のポリシーを提供しています。 以下に、より一般的な例を示します。 <ul> <li> [サイト リストと IE モードEnterpriseサイトを構成する](/deployedge/edge-ie-mode-sitelist)</li><li> [起動、ホーム ページ、および新しいタブ ページの設定を構成する](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)</li> <li> [サーフ ゲームの設定を構成する](/deployedge/microsoft-edge-policies#allowsurfgame)</li> <li> [プロキシ サーバーの設定を構成する](/deployedge/microsoft-edge-policies#proxy-server)</li></ul>
