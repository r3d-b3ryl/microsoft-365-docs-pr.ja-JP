---
title: Microsoft 365 Apps for enterprise
description: アプリを展開Microsoft 365 Apps、更新方法、および設定の管理方法
keywords: 変更履歴
ms.service: m365-md
ms.sitesec: library
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 675b9d32c60febd7e70dfd64f49b7869c489aa0b
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034811"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

## <a name="initial-deployment"></a>初期展開

Microsoft Managed Desktop では、Microsoft 365 Apps for enterprise (64 ビット) がイメージの一部としてすべてのプログラム デバイスに[インストールされます](../service-description/device-list.md)。 次のアプリケーションはすべて、配信時にデバイスに存在する必要があります。

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
> Microsoft Teamsは、Microsoft 365 Apps for enterpriseに展開され、基本イメージには含まれません。 

### <a name="available-deployment-to-users"></a>ユーザーが利用可能な展開

ユーザーが何らかの理由でデバイスにMicrosoft 365 Appsしていない場合は、パッケージを使用してデバイスを予期した状態に戻します。 ユーザーを **モダン Workplace-Office-Office365_Install グループ** に追加すると、アプリはユーザーがアクセスポータル サイト。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for enterprise (32 ビット)

Microsoft Managed Desktop では、エンタープライズ向け M365 Apps の 32 ビット バージョンの展開はサポートされていません。

## <a name="updates-to-microsoft-365-apps"></a>更新プログラムのMicrosoft 365 Apps

Microsoft 365 Apps月次チャネルで更新Enterprise[されます](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)。 この方法では、ユーザーは毎月新しいOffice機能を提供しますが、予測可能なリリース スケジュールで月に 1 回の更新プログラムを受け取る必要があります。 更新プログラムは、月の第 2 火曜日にリリースされます。これらの更新プログラムには、機能、セキュリティ、および品質更新プログラムが含まれます。 これらの更新プログラムは自動的に実行され、その特定のチャネルOffice CDNから直接取得されます。

Microsoft Managed Desktop は、各リリースをずらして、環境内の潜在的な問題を特定します。 アプリ製品グループからのリリースから 28 日後にロールアウトMicrosoft 365完了します。 Microsoft Managed Desktop は、次のように検証とテストの時間を割り当て、リリースをさまざまなグループにスケジュールします。 

- テスト: ゼロ日
- 最初: ゼロ日
- 高速: 3 日
- 広範: 7 日間

Microsoft Managed Desktop は、デバイスの 7 日間の [更新期限](/deployoffice/configure-update-settings-microsoft-365-apps) を設定します。 更新プログラムが利用可能な場合は、7 日以内にインストールする必要があります。 ユーザーには[](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)、期限の 12 時間前にアプリケーション、システム トレイ内の複数の場所で更新プログラムが必要と通知され、期限の 15 分前に警告が表示されます。 更新Microsoft 365 Apps完了するには、すべての更新プログラムを閉じる必要があります。

### <a name="pausing-or-rolling-back-an-update"></a>更新プログラムの一時停止またはロールバック

何らかの理由でアプリの更新プログラムMicrosoft 365一時停止またはロールバックする必要がある場合は、Microsoft [](../working-with-managed-desktop/admin-support.md) Managed Desktop ポータルを通じて管理者サポート要求を送信します。

Microsoft Managed Desktop は、リリース中に、すべてのユーザーのエラー率をMicrosoft 365 Apps。 新しいリリースと先行リリースの品質に大きな違いがある場合は、Microsoft Managed Desktop Admin ポータルを通じてお問い合わせください。 重大度に応じて、リリースを一時停止するか、問題を軽減するための措置を講じてお知らせします。 

### <a name="delivery-optimization"></a>配信の最適化

配信の最適化は、このサービスで利用できるピアツーピア配布Windows 10。 これにより、デバイスは、デバイスがインターネットを通して Microsoft からダウンロードした更新プログラムなどのコンテンツを共有できます。 デバイスが Microsoft から更新プログラムを完全にダウンロードする代わりに、ローカル ネットワーク上の別のデバイスから更新プログラムの一部を取得できるので、この機能を使用すると、ネットワーク帯域幅を削減できます。

[配信の最適化](/deployoffice/delivery-optimization)は、サービス エディションまたはサービス エディションをWindows 10 EnterpriseデバイスWindows 10 Education有効になっています。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>設定によって管理される Microsoft Managed Desktop

Microsoft は、サービスの一部としていくつかの設定を管理します。 Microsoft Managed Desktop では、セキュリティ ベースラインOffice管理は行わないが、[管理するユーザー] セクションのガイダンスに従って、設定[設定](#settings-you-manage)できます。

### <a name="update-settings"></a>設定を更新する

Microsoft Managed Desktop では、管理対象 [デバイスのすべての](/deployoffice/configure-update-settings-microsoft-365-apps) 更新設定が維持され、これらの設定を変更する必要があります。

### <a name="set-updates-to-occur-automatically"></a>更新が自動的に発生するように設定する

**既定値**: 有効

このポリシーは、すべてのデバイスOfficeクラウドから最新の状態に保つ必要がある場合に構成されます。 

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

**既定値**: 月次チャネルEnterpriseチャネル

**UpdatePath** ポリシーと **UpdateChannel** ポリシーの組み合わせは、更新スケジュールを達成するために必要に応じて使用されます。 これらのポリシーは、すべてのデバイスが月次OfficeチャネルのCDN更新プログラムを直接受信Enterprise設定されています。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>ターゲット バージョンの指定Microsoft 365 Apps

ターゲット バージョン ポリシーは、Microsoft Managed Desktop が特定のバージョンのコンピューターをロールバックまたはピン留めするために使用Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>自動更新を有効または無効にするオプションOffice非表示にする

**既定値**: 有効

Microsoft Managed Desktop がアプリケーションの更新ターゲットを満たすには、このMicrosoft 365です。 

### <a name="first-run-settings"></a>最初の実行設定 

初回実行時の動作に影響を与える設定Officeがあります。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>エンド ユーザーに代わってライセンス条項に同意する

**既定値**: 無効

ユーザーがアプリを初めて開Microsoft 365、ライセンス条項に同意するように求めるメッセージが表示されます。 ユーザーに代わってライセンス条項に同意する場合は、Microsoft Managed Desktop Operations チームにサービス要求を送信し、この設定を有効にしてください。 

### <a name="suppress-outlook-mobile-check-box"></a>[モバイルOutlookを抑制する] チェック ボックス

**既定値**: 無効

ユーザーがモバイルを初めて開Outlook、Mobile へのインストールを求Outlookされます。 ユーザーにこのチェック ボックスを表示しない場合は、Microsoft Managed Desktop Operations チームにサービス要求を送信し、デバイスでこの設定を有効にしてください。 

## <a name="other-settings"></a>その他の設定

Microsoft Managed Desktop がMicrosoft 365で構成できる他のアプリ設定があります。 

### <a name="disable-personal-onedrive"></a>個人用アカウントを無効OneDrive

**既定値**: 無効

一部の組織では、デバイス上の企業ファイルと個人ファイルの両方にアクセスできるユーザーを懸念しています。 Microsoft Managed Desktop Operations チームにサービス要求を送信し、この設定を有効にしてください。 

## <a name="settings-you-manage"></a>設定管理する方法

Microsoft Managed Desktop がまだサービスの一部として設定していないポリシーは、他にも多数存在します。 これらのポリシーは、クラウド ポリシー サービスMicrosoft Intune使用する Office[を使用して構成](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)できます。 これらのポリシーを設定するには、次の手順を実行します。

1. Microsoft エンドポイント マネージャー管理センターにサインインします。
2. [**作成] >アプリの [アプリとOfficeポリシー>選択します。**
3. [ポリシー構成 **の作成]** ページで、次の操作を行います。
    - 名前を入力します。
    - 説明を入力します (オプション)。
    - 割 **り当て** で、このポリシーが Microsoft 365 Apps for enterprise のすべてのユーザーに適用されるのか、または Office for the web を使用してドキュメントに匿名でアクセスするユーザーに適用されるのかを選択します。
    - ポリシー構成AAD割り当てられているセキュリティ グループを選択します。 各ポリシー構成は 1 つのグループにのみ割り当て、各グループには 1 つのポリシー構成のみを割り当てることができます。
    - ポリシー構成に含めるポリシー設定を構成します。 ポリシー設定名を検索して、構成するポリシー設定を検索できます。 また、アプリケーション、ポリシーが推奨されるセキュリティ 基準かどうか、およびポリシーが構成されているかどうかをフィルター処理できます。 [プラットフォーム] 列は、ポリシーがデバイス、デバイス、Microsoft 365 Apps for enterprise、またはすべてWindows適用Office for the web示します。
4. 選択が行われたら、[作成] を **選択します**。

> [!NOTE]
> Office構成ポリシーは、ユーザー ベースの展開のみをサポートします
