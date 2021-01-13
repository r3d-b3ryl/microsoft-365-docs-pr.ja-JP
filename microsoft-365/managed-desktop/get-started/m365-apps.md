---
title: Microsoft 365 Apps for enterprise
description: Microsoft 365 Apps の展開方法、更新方法、設定の管理方法
keywords: 変更履歴
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840351"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

## <a name="initial-deployment"></a>初期展開

Microsoft マネージド デスクトップを使用すると、Microsoft 365 Apps for enterprise (64 ビット) がすべてのプログラム デバイスにイメージの一部として [インストールされます](../service-description/device-list.md)。 次のアプリケーションはすべて、配信時にデバイスに存在する必要があります。

- Word
- Excel
- PowerPoint
- Outlook
- 発行者
- Access
- Skype for Business
- OneNote

この方法では、ネットワークへの影響を最小限に抑え、ユーザーがデバイスを受け取り次第、生産性を高めることができます。 その後、管理対象デバイスにさらに多くのポリシーを展開して、使用するアプリケーションをセットアップします。

> [!NOTE]
> Microsoft Teams は、Microsoft 365 Apps for enterprise とは別に展開され、基本イメージには含まれません。 

### <a name="available-deployment-to-users"></a>ユーザーが利用可能な展開

何らかの理由でユーザーのデバイスに Microsoft 365 アプリがインストールされていない場合は、パッケージを使ってデバイスを予期した状態に戻します。 モダン **Workplace-Office-Office365_Install** グループにユーザーを追加すると、ポータル サイトでアプリが利用できます。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for enterprise (32 ビット)

Microsoft マネージド デスクトップでは、M365 Apps for enterprise の 32 ビット バージョンの展開はサポートされていません。

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 アプリの更新プログラム

Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). この方法では、毎月新しい Office 機能をユーザーに提供しますが、予測可能なリリース スケジュールで毎月 1 回の更新プログラムを受信します。 更新プログラムは、毎月第 2 火曜日にリリースされます。これらの更新プログラムには、機能更新プログラム、セキュリティ更新プログラム、品質更新プログラムが含まれる場合があります。 これらの更新は自動的に行われるので、その特定のチャネルの Office CDN から直接取得されます。

Microsoft マネージド デスクトップは、各リリースをずらして、環境内の潜在的な問題を特定します。 Microsoft 365 アプリ製品グループからのリリースの 28 日後にロールアウトが完了します。 Microsoft マネージド デスクトップでは、更新プログラムのリリースをさまざまなグループにスケジュールして、次のように検証とテストに時間を割きます。 

- テスト: ゼロ日
- 最初: ゼロ日
- 高速: 7 日
- 広範: 21 日

Microsoft マネージド デスクトップは、デバイスの 7 日間 [の更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) を設定します。 更新プログラムが利用可能な場合は、7 日以内にインストールする必要があります。 ユーザーには[](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)、期限の 12 時間前にシステム トレイにあるアプリケーションの複数の場所で更新が必要なという通知が表示され、期限の 15 分前に警告が表示されます。 更新を完了するには、すべての Microsoft 365 アプリを終了する必要があります。

### <a name="pausing-or-rolling-back-an-update"></a>更新プログラムの一時停止またはロールバック

何らかの理由で Microsoft 365 アプリの更新プログラムを一時停止またはロールバック[](../working-with-managed-desktop/admin-support.md)する必要がある場合は、Microsoft マネージド デスクトップ ポータルから管理者サポート要求を送信します。

リリース中、Microsoft マネージド デスクトップは、すべての Microsoft 365 アプリのエラー率を監視します。 新しいリリースと先行リリースの品質に大きな違いがある場合は、Microsoft マネージド デスクトップ管理ポータルを通じてお客様にお問い合わせください。 重大度に応じて、リリースを一時停止するか、問題を軽減するための処置を行ったか通知されます。 

### <a name="delivery-optimization"></a>配信の最適化

配信の最適化は、Windows 10 で利用できるピアツーピアの配布テクノロジです。 これにより、デバイスは、インターネットを通して Microsoft からダウンロードした更新プログラムなどのコンテンツを共有できます。 デバイスは、Microsoft から更新プログラムを完全にダウンロードする代わりに、ローカル ネットワーク上の別のデバイスから更新プログラムの一部を取得することができるため、ネットワーク帯域幅の削減に役立ちます。

[配信の](https://docs.microsoft.com/deployoffice/delivery-optimization) 最適化は、Windows 10 Enterprise または Windows 10 Education エディションを実行しているデバイスで既定で有効になっています。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップで管理される設定

Microsoft は、サービスの一部としていくつかの設定を管理します。 Microsoft マネージド デスクトップは、Office セキュリティ基本計画を管理しますが、「管理する設定」セクションのガイダンスに従って自分で[設定できます。](#settings-you-manage)

### <a name="update-settings"></a>設定を更新する

Microsoft マネージド デスクトップでは、 [管理対象デバイスのすべての](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 更新設定が維持されます。これらの設定を変更する必要があります。

### <a name="set-updates-to-occur-automatically"></a>更新が自動的に発生するように設定する

**既定値 :** 有効

このポリシーは、すべてのデバイスOfficeクラウドから最新の状態に保つ必要があります。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>更新プログラムを適用する必要がある期限を設定する

**既定値 :** 7 日

**UpdateDeadline ポリシーは**、更新プログラムがデバイスに適用される前にユーザーが持っている猶予期間を構成するために使用されます。 この期限ポリシーは、ユーザー [に通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) をトリガーして、デバイスに必要な変更をユーザーに通知します。  

### <a name="defer-updates-on-a-device-for-a-period"></a>デバイスの更新プログラムを一期間延期する

このポリシーは、更新プログラム管理デバイス グループごとに異なる方法で構成され、Microsoft マネージド デスクトップが更新ターゲットを満たす必要があります。  

- テスト: ゼロ日
- 最初: ゼロ日
- ファスト 7 日間
- 広範: 21 日

### <a name="update-notifications-settings"></a>通知設定を更新する

**既定値 :** False

Microsoft マネージド デスクトップ デバイスでは、"更新通知を非表示にする" 設定が **False** に設定され、[](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)更新が必要なときにユーザーに通知することで、ユーザーに最適な更新エクスペリエンスを提供できます。

### <a name="specify-a-location-to-look-for-updates"></a>更新プログラムを検索する場所を指定する

**既定値**: 月次エンタープライズ チャネル

**UpdatePath** ポリシーと **UpdateChannel** ポリシーの組み合わせは、更新スケジュールを達成するために必要に応じて使用されます。 これらのポリシーは、すべての Office デバイスが月次エンタープライズ チャネルの更新プログラムを CDN から直接受信するための設定です。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Microsoft 365 アプリのターゲット バージョンを指定する

ターゲット バージョン ポリシーは、特定のバージョンのアプリをロールバックまたはピン留めするために、Microsoft マネージド デスクトップで使用される場合Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>自動更新を有効または無効にするオプションOffice非表示にする

**既定値 :** 有効

この設定は、Microsoft 365 アプリケーションの更新ターゲットを Microsoft マネージド デスクトップが満たすために必要です。 

### <a name="first-run-settings"></a>最初の実行の設定 

初回実行時の動作に影響を与える設定Officeがあります。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>エンド ユーザーの代わりにライセンス条項に同意する

**既定値 :** 無効

ユーザーが初めて Microsoft 365 アプリを開くと、ライセンス条項に同意するように求めるメッセージが表示されます。 ユーザーの代わりにライセンス条項に同意する場合は、Microsoft マネージド デスクトップ 操作チームにサービス要求を送信し、この設定を有効にしてください。 

### <a name="suppress-outlook-mobile-check-box"></a>Outlook モバイルのチェック ボックスを非表示にします。

**既定値 :** 無効

ユーザーが初めて Outlook を開くと、Outlook Mobile のインストールを求めるメッセージが表示されます。 ユーザーにこのチェック ボックスを表示したくない場合は、Microsoft マネージド デスクトップ操作チームにサービス要求を送信し、デバイスでこの設定を有効にしてください。 

## <a name="other-settings"></a>その他の設定

Microsoft マネージド デスクトップでは、必要に応じてユーザーに代わって構成できる他の Microsoft 365 アプリ設定があります。 

### <a name="disable-personal-onedrive"></a>個人用 OneDrive を無効にする

**既定値 :** 無効

一部の組織では、ユーザーがデバイス上の企業ファイルと個人用ファイルの両方にアクセスできると懸念しています。 Microsoft マネージド デスクトップ操作チームにサービス要求を送信して、この設定を有効にできます。 

## <a name="settings-you-manage"></a>管理する設定

Microsoft マネージド デスクトップがサービスの一部としてまだ設定していないポリシーは他にも多数存在します。 これらのポリシーは、Microsoft Intune を使用して構成できます。この Intune では、Office [クラウド ポリシー サービスを使用](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) します。 これらのポリシーを設定するには、次の手順を実行します。

1.  Microsoft Endpoint Manager 管理センターにサインインします。
2.  [ **作成] >アプリの [アプリOfficeポリシー>選択する**
3.  [ポリシー **構成の作成]** ページで、次の操作を行います。
    - 名前を入力します。
    - 説明を入力します (省略可能)。
    - 割 **り** 当てで、このポリシーを Microsoft 365 Apps for enterprise のすべてのユーザーに適用するか、Office for the web を使用してドキュメントに匿名でアクセスするユーザーに適用するか選択します。
    - ポリシー構成に割り当てられている AAD ベースのセキュリティ グループを選択します。 各ポリシー構成は 1 つのグループにのみ割り当て、各グループには 1 つのポリシー構成のみを割り当てることができます。
    - ポリシー構成に含めるポリシー設定を構成します。 ポリシー設定名を検索して、構成するポリシー設定を検索できます。 また、ポリシーが推奨されるセキュリティベースラインかどうか、およびポリシーが構成されているかどうかを基に、アプリケーションをフィルター処理できます。 プラットフォーム列は、ポリシーが Microsoft 365 Apps for enterprise for Windows デバイス、Office for the web、またはすべてに適用されるかどうかを示します。
4.  選択が行われたら、[作成] を選択 **します**。

> [!NOTE]
> Officeポリシーは、ユーザー ベースの展開のみをサポートします。
