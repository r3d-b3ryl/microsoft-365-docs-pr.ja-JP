---
title: Microsoft 365 Apps for enterprise
description: Microsoft 365 Apps の展開方法、更新方法、および設定の管理方法
keywords: 変更履歴
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f8dd666c41863192d866693c6860a64064f846e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904854"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

## <a name="initial-deployment"></a>初期展開

Microsoft Managed Desktop を使用すると、Microsoft 365 Apps for enterprise (64 ビット) がイメージの一部としてすべてのプログラム デバイスにインストール [されます](../service-description/device-list.md)。 次のアプリケーションはすべて、配信時にデバイスに存在する必要があります。

- Word
- Excel
- PowerPoint
- Outlook
- 発行者
- Access
- Skype for Business
- OneNote

この方法では、ネットワークへの影響を最小限に抑え、ユーザーがデバイスを受け取り次第、生産性を高めることができます。 その後、使用するアプリケーションをセットアップするために、管理対象デバイスにさらに多くのポリシーを展開します。

> [!NOTE]
> Microsoft Teams は、エンタープライズ向け Microsoft 365 Apps とは別に展開され、基本イメージには含まれません。 

### <a name="available-deployment-to-users"></a>ユーザーが利用可能な展開

ユーザーが何らかの理由でデバイスに Microsoft 365 Apps をインストールしていない場合は、パッケージを使用してデバイスを予期した状態に戻します。 ユーザーを **モダン Workplace-Office-Office365_Installグループ** に追加すると、ポータル サイトでアプリを利用できます。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for enterprise (32 ビット)

Microsoft Managed Desktop では、エンタープライズ向け M365 Apps の 32 ビット バージョンの展開はサポートされていません。

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 アプリの更新

Microsoft 365 Apps は、月次エンタープライズ チャネル [で更新する設定です](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)。 この方法では、ユーザーは毎月新しいOffice機能を提供しますが、予測可能なリリース スケジュールで月に 1 回の更新プログラムを受け取る必要があります。 更新プログラムは、月の第 2 火曜日にリリースされます。これらの更新プログラムには、機能、セキュリティ、および品質更新プログラムが含まれます。 これらの更新プログラムは自動的に実行され、その特定のチャネルOffice CDN から直接取得されます。

Microsoft Managed Desktop は、各リリースをずらして、環境内の潜在的な問題を特定します。 Microsoft 365 App 製品グループからのリリースから 28 日後にロールアウトを完了します。 Microsoft Managed Desktop は、次のように検証とテストの時間を割り当て、リリースをさまざまなグループにスケジュールします。 

- テスト: ゼロ日
- 最初: ゼロ日
- 高速: 3 日
- 広範: 7 日間

Microsoft Managed Desktop は、デバイスの 7 日間の [更新期限](/deployoffice/configure-update-settings-microsoft-365-apps) を設定します。 更新プログラムが利用可能な場合は、7 日以内にインストールする必要があります。 ユーザーには[](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)、期限の 12 時間前にアプリケーション、システム トレイ内の複数の場所で更新プログラムが必要と通知され、期限の 15 分前に警告が表示されます。 更新プログラムを完了するには、すべての Microsoft 365 アプリを閉じる必要があります。

### <a name="pausing-or-rolling-back-an-update"></a>更新プログラムの一時停止またはロールバック

何らかの理由で Microsoft 365 アプリの更新プログラムを一時停止またはロールバック[](../working-with-managed-desktop/admin-support.md)する必要がある場合は、Microsoft Managed Desktop ポータルを介して管理者サポート要求を送信します。

リリース中、Microsoft Managed Desktop は、すべての Microsoft 365 アプリのエラー率を監視します。 新しいリリースと先行リリースの品質に大きな違いがある場合は、Microsoft Managed Desktop Admin ポータルを通じてお問い合わせください。 重大度に応じて、リリースを一時停止するか、問題を軽減するための措置を講じてお知らせします。 

### <a name="delivery-optimization"></a>配信の最適化

配信の最適化は、Windows 10 で利用できるピアツーピア配布テクノロジです。 これにより、デバイスは、デバイスがインターネットを通して Microsoft からダウンロードした更新プログラムなどのコンテンツを共有できます。 デバイスが Microsoft から更新プログラムを完全にダウンロードする代わりに、ローカル ネットワーク上の別のデバイスから更新プログラムの一部を取得できるので、この機能を使用すると、ネットワーク帯域幅を削減できます。

[Windows](/deployoffice/delivery-optimization) 10 Enterprise エディションまたは Windows 10 Education エディションを実行しているデバイスでは、配信の最適化が既定で有効になっています。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop によって管理される設定

Microsoft は、サービスの一部としていくつかの設定を管理します。 Microsoft Managed Desktop では、セキュリティ ベースラインOffice管理は行わないが、[管理する設定] セクションのガイダンスに従って、自分で[設定できます。](#settings-you-manage)

### <a name="update-settings"></a>設定を更新する

Microsoft Managed Desktop では、管理対象 [デバイスのすべての](/deployoffice/configure-update-settings-microsoft-365-apps) 更新設定が維持され、これらの設定を変更する必要があります。

### <a name="set-updates-to-occur-automatically"></a>更新が自動的に発生するように設定する

**既定値**: 有効

このポリシーは、すべてのデバイスがクラウドOffice最新の状態に保たれするように構成されています。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>更新プログラムを適用する必要がある期限を設定する

**既定値**: 7 日間

**UpdateDeadline ポリシーは**、更新プログラムがデバイスに適用される前にユーザーが持つ猶予期間を構成するために使用されます。 この期限ポリシーは、ユーザーに [通知](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) をトリガーして、デバイスで必要な変更をユーザーに通知します。  

### <a name="defer-updates-on-a-device-for-a-period"></a>デバイスの更新プログラムを一期間延期する

このポリシーは、更新プログラム管理デバイス グループごとに異なる構成であり、Microsoft Managed Desktop が更新ターゲットを満たすために必要です。  

- テスト: ゼロ日
- 最初: ゼロ日
- 高速 7 日
- 広範: 21 日

### <a name="update-notifications-settings"></a>通知の設定を更新する

**既定値**: False

Microsoft Managed Desktop デバイスの "更新通知を非表示にする" 設定は **False** に設定され [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)、更新プログラムが必要なときにユーザーに通知することで、ユーザーに最適な更新エクスペリエンスを提供します。

### <a name="specify-a-location-to-look-for-updates"></a>更新プログラムを検索する場所を指定する

**既定値**: 月次エンタープライズ チャネル

**UpdatePath** ポリシーと **UpdateChannel** ポリシーの組み合わせは、更新スケジュールを達成するために必要に応じて使用されます。 これらのポリシーは、すべてのデバイスが月次エンタープライズ チャネルOffice CDN から更新プログラムを直接受信するために設定されています。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Microsoft 365 アプリのターゲット バージョンを指定する

ターゲット バージョン ポリシーは、Microsoft Managed Desktop が特定のバージョンのデスクトップをロールバックまたはピン留めするために使用Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>自動更新を有効または無効にするオプションOffice非表示にする

**既定値**: 有効

Microsoft Managed Desktop が Microsoft 365 アプリケーションの更新ターゲットを満たすには、この設定が必要です。 

### <a name="first-run-settings"></a>最初の実行設定 

最初に実行する動作に影響を与える設定Officeがあります。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>エンド ユーザーに代わってライセンス条項に同意する

**既定値**: 無効

ユーザーが Microsoft 365 アプリを初めて開くと、ライセンス条項に同意するように求めるメッセージが表示されます。 ユーザーに代わってライセンス条項に同意する場合は、Microsoft Managed Desktop Operations チームにサービス要求を送信し、この設定を有効にしてください。 

### <a name="suppress-outlook-mobile-check-box"></a>[Outlook モバイルを抑制する] チェック ボックス

**既定値**: 無効

ユーザーが初めて Outlook を開くと、Outlook Mobile のインストールを求めるメッセージが表示されます。 ユーザーにこのチェック ボックスを表示しない場合は、Microsoft Managed Desktop Operations チームにサービス要求を送信し、デバイスでこの設定を有効にしてください。 

## <a name="other-settings"></a>その他の設定

その他の Microsoft 365 アプリ設定は、Microsoft Managed Desktop が必要に応じてユーザーに代わって構成できます。 

### <a name="disable-personal-onedrive"></a>個人用 OneDrive を無効にする

**既定値**: 無効

一部の組織では、デバイス上の企業ファイルと個人ファイルの両方にアクセスできるユーザーを懸念しています。 Microsoft Managed Desktop Operations チームにサービス要求を送信し、この設定を有効にしてください。 

## <a name="settings-you-manage"></a>管理する設定

Microsoft Managed Desktop がまだサービスの一部として設定していないポリシーは、他にも多数存在します。 これらのポリシーは、Microsoft Intune を使用して構成できます。このポリシーは、クラウド Office [サービスを使用](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) します。 これらのポリシーを設定するには、次の手順を実行します。

1.  Microsoft Endpoint Manager 管理センターにサインインします。
2.  [ **作成] >アプリの [アプリとOfficeポリシー>選択します。**
3.  [ポリシー構成 **の作成]** ページで、次の操作を行います。
    - 名前を入力します。
    - 説明を入力します (オプション)。
    - 割 **り** 当てで、このポリシーが Microsoft 365 Apps for enterprise のすべてのユーザーに適用されるのか、または web の Office を使用してドキュメントに匿名でアクセスするユーザーに適用されるのかを選択します。
    - ポリシー構成に割り当てられている AAD ベースのセキュリティ グループを選択します。 各ポリシー構成は 1 つのグループにのみ割り当て、各グループには 1 つのポリシー構成のみを割り当てることができます。
    - ポリシー構成に含めるポリシー設定を構成します。 ポリシー設定名を検索して、構成するポリシー設定を検索できます。 また、アプリケーション、ポリシーが推奨されるセキュリティ 基準かどうか、およびポリシーが構成されているかどうかをフィルター処理できます。 [プラットフォーム] 列は、ポリシーが Microsoft 365 Apps for enterprise for Windows デバイス、Office、またはすべてに適用されるかどうかを示します。
4.  選択が行われたら、[作成] を **選択します**。

> [!NOTE]
> Office構成ポリシーは、ユーザー ベースの展開のみをサポートします。