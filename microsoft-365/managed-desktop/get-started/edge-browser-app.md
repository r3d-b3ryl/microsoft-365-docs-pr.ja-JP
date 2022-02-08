---
title: Microsoft Edge
description: ブラウザーを展開Microsoft Edge更新する方法について説明します。
keywords: ブラウザー, Microsoft Managed Desktop, Microsoft 365, サービス, ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: aab02ec260f0131ab32d28834152f50b84abce21
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444607"
---
# <a name="microsoft-edge"></a>Microsoft Edge

[Microsoft Edgeは](https://www.microsoft.com/edge)、次の世界クラスのパフォーマンスと価値を提供します。

- 外部からの脅威からプライバシーと保護を強化します。
- アプリ、ファイル、サイトOffice組み込みアプリケーションへの生産性の迅速なMicrosoft Search。
- クロスプラットフォームサポートとプロファイルを使用してデバイス間で同期することでシームレスなエクスペリエンスを実現します。

> [!IMPORTANT]
> Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、「 [FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)」を参照してください)。 現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。 [詳細については、こちらを参照してください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

## <a name="updates-to-microsoft-edge"></a>ユーザーの更新Microsoft Edge

Microsoft Managed Desktop は、8 週間[](/deployedge/microsoft-edge-channels#extended-stable-channel)ごとに自動的に更新Microsoft Edgeの拡張安定チャネルを展開します。 拡張安定チャネルの更新プログラムは、顧客に[](/deployedge/microsoft-edge-update-progressive-rollout)最適なエクスペリエンスを確保するために、Microsoft Edgeグループによって段階的に展開されます。

ベータ [チャネルは](/deployedge/microsoft-edge-channels#beta-channel) 、組織内の代表的な検証のためにテスト グループ内のデバイスに展開されます。 このチャネルは、約 4 週間ごとに完全にサポートされ、新しい機能で自動的に更新されます。

> [!IMPORTANT]
> 更新プログラムがMicrosoft Edge確認するには、更新ポリシーを変更Microsoft Edge[しません](/deployedge/microsoft-edge-update-policies)。

## <a name="settings-managed-by-microsoft-managed-desktop"></a>設定によって管理される Microsoft Managed Desktop

Microsoft Managed Desktop では、ブラウザーをセキュリティで保護するために、Microsoft Edgeポリシーのセットを作成しました。 既定のブラウザー設定は次のとおりです。

### <a name="microsoft-edge-extensions"></a>Microsoft Edge拡張機能

Microsoft Managed Desktop デバイスMicrosoft Edgeセキュリティベースラインは、すべての Chrome 拡張機能を無効にし、ユーザーをセキュリティで保護するための 2 つのポリシーを設定します。 環境で拡張機能を有効にして展開するには、「管理する設定[」を参照してください](#settings-you-manage)。

| 設定 | 既定値 | 説明 |
| ------ | ------ | ------ |
| 拡張機能のインストール ブロックリスト | すべて | Microsoft Managed Desktop は、Chrome 拡張機能が管理エンドポイントにインストールされるのを防ぐために、このポリシーを設定します。 データ損失の保護、プライバシー、およびデバイスを侵害する可能性のあるその他のリスクなど、Chromium拡張機能モデルに関連する既知のリスクがあります。 |
| ユーザー レベルのネイティブ メッセージング ホストを許可する (管理者のアクセス許可なしでインストール) | 無効 | このポリシーを無効にすると、Microsoft Edgeシステム レベルにインストールされているネイティブ メッセージング ホストだけが使用されます。 ネイティブ メッセージング ホストは Chrome 拡張機能の一部で、ブラウザーがユーザーのエンドポイントの他の部分と対話し、さまざまなセキュリティ上の問題を引き起こす可能性があります。 |

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

| 設定 | 既定値 | 説明
| ------ | ------ | ------ |
| TLS の最小バージョン | サポートされる最小 TLS 1.2 | 安全性の低い TLS 1.1 を使用する場合は、要求を送信できます。 |
| ユーザーが SSL 警告ページから進むのを許可する | 無効 | ユーザーが TSL エラーのあるサイトにアクセスできるので、この設定を有効にすることをお勧めしません。 |

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

| 設定 | 既定値 | 説明
| ------ | ------ | ------ |
| SmartScreen Windows Defender構成する | 有効 | ユーザーの保護に役立つ既定で有効になっています。 |
| Windows Defenderの SmartScreen プロンプトの表示 | 有効 | この設定を無効にしても、ユーザーは警告を無視し、悪意のあるサイトを引き続き使用できます。 |
| ダウンロードに関する SmartScreen Windows Defenderのバイパスを防止する | 有効 | ユーザーが警告を無視して未確認のダウンロードを完了できるので、この設定を無効にすることをお勧めしません。 |

### <a name="adobe-flash"></a>Adobe Flash

| 設定 | 既定値 | 説明
| ------ | ------ | ------ |
| Adobe Flash の既定の設定 | 無効 | 関連付けられたセキュリティ リスクのため、Flash の使用はお勧めしません。 <br><br> Flash に依存するプロセスがまだ存在する場合は、 **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ポリシーを設定して、必要なサイトで Flash を有効にしてください。 Flash を使用するサイトの許可リストを維持できない場合は、変更要求を送信して値を [Click **to Play**] に変更します。これにより、ユーザーは Flash の実行が適切なときに選択できます。 |

### <a name="password-manager"></a>パスワード マネージャー

| 設定 | 既定値 | 説明
| ------ | ------ | ------ |
| パスワード マネージャーへのパスワードの保存を有効にする | 無効 | パスワード マネージャーは既定で無効になっています。 この機能を有効にする場合は、サポート要求を送信し、サービス エンジニアが環境内で設定を有効にできます。 |

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer モード (Microsoft Edge

Microsoft Edge で IE モードを利用すると、組織が必要とするすべてのサイトを 1 つのブラウザーで簡単に使用できます。 この機能は、Chromiumレンダリング エンジンと互換性のあるサイトに統合Chromium使用します。 Microsoft Edgeは、IE 機能に依存していない、または依存関係を持つサイトに対して、Internet Explorer 11 (IE11) の Trident MSHTML エンジンを使用します。 [詳細情報](/DeployEdge/edge-ie-mode)

Microsoft Managed Desktop では、既定Internet Explorerデバイスの管理モードが有効になります。

| 設定 | 既定値 | 説明
| ------ | ------ | ------ |
| Internet Explorerモードの統合 | Internet Explorer モード | 既定では、デバイスは Internet Explorer モードを使用Internet Explorer設定できます。 この動作を変更するには、サポート要求を送信します。 |
| サイトを Enterprise モード サイト一覧に追加する | 説明を参照してください。 | サイトをサイト モードでInternet Explorerするには、[サイト] リストにサイトをEnterprise[する必要があります](/DeployEdge/edge-ie-mode-sitelist)。 サイト一覧のEnterprise展開は、お客様の責任です。 詳細については、「Configure [using the Configure using the Configure using the Configure Enterprise モード サイト リスト ポリシー」を参照してください](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)。 |

### <a name="other-settings"></a>その他の設定

| 設定 | 既定値 | 説明
| ------ | ------ | ------ |
| すべてのサイトでサイトの分離を有効にする | 有効 | このポリシーを有効にすると、ユーザーは、各サイトが独自のプロセスで実行される既定の動作をオプトアウトできません。 |
| サポートされている認証スキーム | NTLM、ネゴシエート | Microsoft Managed Desktop では、基本認証またはダイジェスト認証スキームはサポートされていません。 |
| 最初の実行時に別のブラウザーのデータと設定を自動的にインポートする | サポートされているすべてのデータ型と設定を既定のブラウザーから自動的にインポートします。 | このポリシーを適用すると、最初の実行エクスペリエンスはインポート セクションをスキップし、ユーザーの操作を最小限に抑える。 この設定に関係なく、Microsoft Edgeの古いバージョンのブラウザー データは、最初の実行時に常にサイレント モードで移行されます。 |

## <a name="settings-you-manage"></a>設定管理する方法

[管理用テンプレート] プロファイルMicrosoft Edge使用して、前に説明していない任意の設定を展開Microsoft Intune。 詳細については、「Configure [Microsoft Edge ポリシー設定」を参照Microsoft Intune](/deployedge/configure-edge-with-intune)。 Intune の Microsoft Edge 管理用テンプレートに現在含まれていないポリシーを評価する場合は、Intune の Windows 10 デバイスのカスタム設定を使用できます。

| 設定 | 説明
| ------ | ------ |
| 特定の Chrome 拡張機能を有効にする | 管理用テンプレートには、特定の Chrome 拡張機能を展開する設定が用意Microsoft Intune。 [コンピューターの構成] [**拡張機能] > Microsoft Edge >[>特定の拡張機能のインストールを許可する] で確認できます**。 |
| 拡張機能をサイレント インストールする | 管理用テンプレートを使用して、ユーザーにMicrosoft Edge拡張機能をインストールするように設定することもできます。 [コンピューターの構成] [拡張機能] > Microsoft Edge >[>にインストールされている **拡張機能を制御する] で確認できます**。 |
| Microsoft Edge更新ポリシー | 更新プログラムがMicrosoft Edge確認するには、更新ポリシーを変更Microsoft Edge[しません](/deployedge/microsoft-edge-update-policies)。 |
| その他の一般的なエンタープライズ ポリシー | Microsoft Edge多くの他のポリシーを提供しています。 以下に、より一般的な例を示します。 <ul> <li> [サイト リストと IE モードEnterpriseサイトを構成する](/deployedge/edge-ie-mode-sitelist)</li><li> [起動、ホーム ページ、および新しいタブ ページの設定を構成する](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)</li> <li> [サーフ ゲームの設定を構成する](/deployedge/microsoft-edge-policies#allowsurfgame)</li> <li> [プロキシ サーバーの設定を構成する](/deployedge/microsoft-edge-policies#proxy-server)</li></ul>
