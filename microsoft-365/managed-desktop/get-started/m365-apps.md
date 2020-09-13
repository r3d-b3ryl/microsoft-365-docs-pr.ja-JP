---
title: Microsoft 365 Apps for enterprise
description: Microsoft 365 アプリの展開方法、更新方法、および設定の管理方法
keywords: 変更履歴
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547748"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

## <a name="initial-deployment"></a>初期展開

Microsoft マネージドデスクトップでは、Microsoft 365 Apps for enterprise (64 ビット) は、すべての [プログラムデバイス](../service-description/device-list.md)上のイメージの一部としてインストールされます。 次のすべてのアプリケーションが、配信時にデバイス上に存在する必要があります。

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype for Business
- OneNote

この方法では、ネットワークへの影響を最小限に抑え、ユーザーがデバイスを受信するとすぐに生産性を向上させることができます。 その後、管理対象デバイスに追加のポリシーを展開して、使用するアプリケーションを設定します。

> [!NOTE]
> Microsoft Teams は、Microsoft 365 enterprise 用アプリとは別に展開され、基本イメージには含まれていません。 

### <a name="available-deployment-to-users"></a>ユーザーに対して使用可能な展開

ユーザーが何らかの理由で、デバイス上に Microsoft 365 アプリを持っていない場合は、パッケージを使用してデバイスを予期した状態に戻すことができます。 **モダンワークプレース-Office Office365_Install**グループにユーザーを追加すると、会社のポータルでアプリを使用できるようになります。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 enterprise 用アプリ (32 ビット)

Microsoft マネージドデスクトップでは、32ビットバージョンの M365 Apps for enterprise を展開することはサポートされていません。

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 アプリの更新

Microsoft 365 アプリは [月次エンタープライズチャネル](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)で更新するように設定されています。 この方法では、ユーザーに毎月新しい Office の機能が提供されますが、予測可能なリリーススケジュールに従って1か月あたりの更新プログラムを1つだけ受け取ることができます。 更新プログラムは月の第2火曜日にリリースされます。これらの更新プログラムには、機能、セキュリティ、および品質の更新が含まれます。 これらの更新プログラムは自動的に実行され、その特定のチャネルの Office CDN から直接プルされます。

Microsoft マネージドデスクトップでは、各リリースが環境内の潜在的な問題を識別するために staggers れます。 Microsoft 365 App product グループからのリリース後、28日以内に公開を完了します。 Microsoft マネージドデスクトップでは、次のように、別のグループにリリースを更新して、検証とテストの時間を確保します。 

- テスト: 0 日
- 最初: 0 日
- Fast: 7 日間
- 広範:21 日

Microsoft マネージドデスクトップでは、デバイスの [更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) が7日間に設定されています。 更新プログラムが利用可能になったら、7日以内にインストールする必要があります。 ユーザーには、いくつかの場所で更新が必要であることが [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) されます。これは、システムトレイの期限よりも12時間前に、その期限よりも前に警告を表示します。 更新を完了するには、すべての Microsoft 365 アプリを閉じる必要があります。

### <a name="pausing-or-rolling-back-an-update"></a>更新プログラムの一時停止またはロールバック

何らかの理由で Microsoft 365 アプリの更新を一時停止またはロールバックする必要がある場合は、Microsoft マネージドデスクトップポータルを使用して [管理者サポート要求](../working-with-managed-desktop/admin-support.md) をファイルします。

Microsoft マネージドデスクトップでは、リリース中にすべての Microsoft 365 アプリのエラー率が監視されます。 新しいリリースとその先行タスクの間で品質に著しい違いがある場合は、Microsoft Managed Desktop 管理ポータルにお問い合わせください。 重要度によっては、リリースを一時停止するかどうかを確認するか、問題を緩和するための処置が行われたことを知らせます。 

### <a name="delivery-optimization"></a>配信の最適化

配信の最適化は、Windows 10 で使用できるピアツーピアの配布テクノロジです。 これにより、デバイスがインターネット経由で Microsoft からダウンロードしたコンテンツ (更新プログラムなど) を共有できるようになります。 これにより、デバイスは、Microsoft から更新プログラムを完全にダウンロードするのではなく、ローカルネットワーク上の別のデバイスから更新プログラムの一部を取得できるので、ネットワーク帯域幅を減らすことができます。

既定では、[配信の最適化](https://docs.microsoft.com/deployoffice/delivery-optimization)は、Windows 10 Enterprise または windows 10 のエデュケーションエディションを実行しているデバイスで有効になっています。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップによって管理される設定

Microsoft では、一部の設定をサービスの一部として管理しています。 Microsoft マネージドデスクトップは Office セキュリティベースラインを管理していませんが、自分で設定するには、[ [管理の設定](#settings-you-manage) ] セクションのガイダンスに従ってください。

### <a name="update-settings"></a>設定を更新する

Microsoft マネージドデスクトップでは、管理対象デバイスのすべての [更新設定](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) が保持されており、これらの設定を変更する必要があります。

### <a name="set-updates-to-occur-automatically"></a>更新が自動的に発生するように設定する

**既定値**: 有効

このポリシーは、クラウドからすべての Office デバイスを最新の状態に保つために構成されます。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>更新プログラムを適用する期限を設定する

**既定値**は次のとおりです。7日

**Updatedeadline 期限**ポリシーは、更新がデバイスに適用されるまでのユーザーの猶予期間を構成するために使用されます。 この期限ポリシーでは、ユーザーに対して、デバイスで必要な変更について [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) することもトリガーされます。  

### <a name="defer-updates-on-a-device-for-a-period"></a>デバイス上の更新プログラムを一定期間保留する

このポリシーは、更新管理デバイスグループごとに異なる方法で構成されており、更新の対象を満たすために Microsoft マネージドデスクトップに必要です。  

- テスト: 0 日
- 最初: 0 日
- ファスト7日
- 広範:21 日

### <a name="update-notifications-settings"></a>通知の設定を更新する

**既定値**: False

Microsoft マネージドデスクトップデバイスで [更新通知を表示しない] 設定が **False** に設定されている場合は、更新が必要なときに [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) することで、ユーザーに最高の更新プログラムを提供します。

### <a name="specify-a-location-to-look-for-updates"></a>更新プログラムを検索する場所を指定する

**既定値**: 月次エンタープライズチャネル

更新スケジュールを設定するには、必要に応じて、 **Updatepath** ポリシーと **UpdateChannel** ポリシーの組み合わせを使用します。 これらのポリシーは、すべての Office デバイスが毎月のエンタープライズチャネルの CDN から直接更新を受信するように設定されています。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Microsoft 365 アプリのターゲットバージョンを指定する

ターゲットバージョンポリシーは、特定のバージョンの Office をロールバックまたは pin するために Microsoft マネージドデスクトップによって使用される場合があります。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Office 自動更新を有効または無効にするオプションを非表示にする

**既定値**: 有効

Microsoft マネージドデスクトップでは、Microsoft 365 アプリケーションの更新対象を満たすために、この設定が必要になります。 

### <a name="first-run-settings"></a>最初の実行時の設定 

Office の初回実行時の動作に影響を与える設定がいくつかあります。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>エンドユーザーの代わりにライセンス条項に同意する

**既定値**: 無効

ユーザーが Microsoft 365 アプリを初めて開いたときに、ライセンス条項に同意するように求めるメッセージが表示されます。 ユーザーの代わりにライセンス条項に同意する場合は、この設定を有効にするように Microsoft Managed Desktop Operations team にサービス要求をファイルします。 

### <a name="suppress-outlook-mobile-check-box"></a>Outlook mobile の非表示のチェックボックス

**既定値**: 無効

ユーザーが初めて Outlook を開いたときに、Outlook Mobile をインストールするように求めるメッセージが表示されます。 このチェックボックスが表示されないようにするには、Microsoft Managed Desktop Operations team に対してサービス要求を実行し、デバイスでこの設定を有効にするように求めます。 

## <a name="other-settings"></a>その他の設定

Microsoft のマネージドデスクトップは、必要に応じて、お客様365の代わりに設定することもできます。 

### <a name="disable-personal-onedrive"></a>個人用 OneDrive を無効にする

**既定値**: 無効

組織によっては、デバイス上の企業および個人の両方のファイルにアクセスするユーザーに懸念があります。 この設定を有効にするには、Microsoft Managed Desktop Operations teams を使用してサービス要求をファイルにすることができます。 

## <a name="settings-you-manage"></a>管理する設定

Microsoft Managed Desktop がまだサービスの一部として設定されていないその他のポリシーが多数あります。 これらは、 [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service を使用する Microsoft Intune を使用して構成できます。 これを行うには、次の手順を実行します。

1.  Microsoft エンドポイントマネージャー管理センターにサインインします。
2.  **Office アプリのアプリ > ポリシーの選択 > 作成**
3.  [ポリシー構成の **作成** ] ページで、次の操作を行います。
    - 名前を入力します。
    - 説明を入力します (省略可能)。
    - [ **割り当て**] で、このポリシーを Microsoft 365 Apps のすべてのユーザーに適用するか、または web 用に Office を使用してドキュメントに匿名でアクセスするユーザーに対して行うかを選択します。
    - ポリシー構成に割り当てられている AAD ベースのセキュリティグループを選択します。 各ポリシー構成は1つのグループにのみ割り当てることができ、各グループには1つのポリシー構成しか割り当てることができません。
    - ポリシーの構成に含めるポリシー設定を構成します。 ポリシー設定名を検索して、構成するポリシー設定を見つけることができます。 また、ポリシーが推奨セキュリティベースラインであるかどうか、およびポリシーが構成されているかどうかについて、アプリケーションに対してフィルター処理することもできます。 [プラットフォーム] 列は、ポリシーが Microsoft 365 アプリ for enterprise for Windows のデバイス、web 用の Office、またはすべてに適用されているかどうかを示します。
4.  選択を行った後、[ **作成**] を選択します。

> [!NOTE]
> Office 構成ポリシーは、ユーザーベースの展開のみをサポートします。
