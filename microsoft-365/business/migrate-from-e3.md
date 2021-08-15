---
title: ビジネスからMicrosoft 365に移行Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: サブスクリプションを持Office 365 E3 300 人を超える従業員がいない場合は、サブスクリプションへの切り替Microsoft 365 Business Premium。
ms.openlocfilehash: 89bf493b39250d88fcb47585d71e7dadd6600c4c3fff0658bb72e51b9ff386c5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53837665"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Office 365 E3からMicrosoft 365 Business Premium

Microsoft 365 Business Premiumは、クラス最高のクラウドベースの生産性アプリと簡単なデバイス管理とセキュリティを組み合わせて、中小企業に必要なすべてを備えています。 現在、サブスクリプションを持Office 365 E3 300 人を超える従業員がいない場合は、セキュリティ機能を追加するために Microsoft 365 Business Premium に切り替えて検討してください。

移行は簡単です。最初にライセンスを切り替えて、現在のサブスクリプション内のすべてのデータとユーザー情報が維持されます。 移行後は、アプリに追加される機能を設定する必要Microsoft 365 Business Premium。

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>データとOffice 365 E3の違Microsoft 365 Business Premium

次の表は、データとMicrosoft 365 Business Premiumの違Office 365 E3。

| 特徴    | Microsoft 365 Business Premium    | Office 365 E3 |
|:-------|:-----|:-----|
| **社内**        | | |
| Officeアプリ<sup>1</sup>    | Microsoft 365 Apps for business    | Microsoft 365 Apps for enterprise |
| **クラウド生産性アプリ**        | | |
| Exchange OnlineとOutlook    | メールボックスあたり 50 GB のストレージ制限と無制限のストレージExchange Online Archiving    | メールボックスあたり 100 GB のストレージ制限と無制限の容量Exchange Online Archiving |
| Teams    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データにOffice 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | ユーザーあたり 1 TB のストレージ制限    | 無制限 | 
| Yammer, SharePoint, Planner, Stream    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データにOffice 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データにOffice 365 E3](../media/check-mark.png) |
| **脅威保護**        | | |
| Microsoft Defender for Office 365 プラン 1 | ![Microsoft 365 Business Premium](../media/check-mark.png)    | 含まれていませんが、追加できます |
| **ID 管理**        | | |
| ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービス パスワードリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス ID のパスワード 書き戻し|     ![Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| **デバイスおよびアプリの管理**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| 共有コンピューターのライセンス認証|     ![Microsoft 365 Business Premium](../media/check-mark.png)    | ![データにOffice 365 E3](../media/check-mark.png)| 
| Win 7/8.1 Windows 10 ProライセンスからライセンスへのアップグレードProする|     ![Microsoft 365 Business Premium](../media/check-mark.png)    ||
| **情報保護**        | | |
|Office 365 データ損失防止|    ![Microsoft 365 Business Premium](../media/check-mark.png)|![データにOffice 365 E3](../media/check-mark.png)|
|Azure Information Protection Plan 1, BitLocker の適用|![Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Plan 1, Sensitivity labels|![Microsoft 365 Business Premium](../media/check-mark.png)||
|**クライアント アクセス ライセンス (CAL 権限)**|||
|EnterpriseCAL スイート (Exchange、SharePoint、Skype)||![データにOffice 365 E3](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 Business Premium Office アプリの Office バージョンには、グループ ポリシー、アプリの利用統計情報、更新コントロール、スプレッドシートの比較と照会、またはビジネス インテリジェンスによるボリュームのアクティブ化は含まれています。

## <a name="migration"></a>移行

サブスクリプションを移行するには、「少数[のユーザー](../commerce/subscriptions/change-plans-manually.md)をユーザーに移行する場合は、手動でプランを変更する」を参照Microsoft 365 Business Premium。 また、すべてのユーザー[を自動的](../commerce/subscriptions/upgrade-to-different-plan.md)にアップグレードしたり、パートナーと一緒に E3 サブスクリプションとライセンスを別のサブスクリプションにMicrosoft 365 Business Premiumすることもできます。
次のセクションでは、必要な変更がある場合は変更し、移行後に実行できる操作について説明します。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3の構成とデータ
移行する前に、現在のサブスクリプションまたはデータに変更を加える必要は一切ない。これには次の内容が含まれます。

- DNS レコードやドメイン名などのサブスクリプション構成。
- 多要素認証や条件付きアクセス ポリシーなどのユーザー アカウントとグループ アカウントと認証設定。
- 生産性向上サービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。
- Officeアプリケーションは自動的に拡張されます。 Office 365では、72 時間ごとにユーザーのライセンス割り当てを確認し、Office アプリケーションをユーザー サブスクリプションに一致するバージョンに変換します。

### <a name="windows-10"></a>Windows 10

Creator のWindowsにまだインストールされていない場合はWindows Pro [Creators Update](upgrade-to-windows-pro-creators-update.md)にアップグレードWindows Proしてください。

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>ユーザーデバイスとファイルを保護するためのポリシーの設定

> [!NOTE]
> MDM ポリシーとデバイスOffice 365設定した場合、これらのデバイスはデバイス の [デバイス] ページに表示Microsoft 365 管理センター。 設定したポリシーは、Intune ポータルのクラシック ポリシーの一覧に [表示されます](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)。

ユーザーにライセンスを割り当Microsoft 365 Business Premium、ユーザーのデバイスとファイルの保護を開始できます。

組織内のすべてのユーザーを Microsoft 365 Business Premium にアップグレードした場合は、[ホーム] ページにセットアップ ウィザードが表示され、セットアップ ウィザードの手順で[[Microsoft 365 Business Premium](set-up.md)のセットアップ] に従ってファイルとモバイル デバイスを保護できます。

[デバイス] ページで、次の手順を実行することもできます。
  
1. 管理センターの左側のナビゲーションで、[デバイス ポリシー]  \> **に移動します**。

2. [デバイス ポリシー **] ページで、[** 追加] を **選択します**。

3. [ポリシー **の追加]** ウィンドウでポリシーに名前を付け、ドロップダウンから **[ポリシー** の種類] を選択します。

     Android デバイスと iPhone デバイス、および Windows 10 でファイルを保護するためのアプリケーション ポリシーを設定し、会社所有の Windows 10 デバイスのデバイス構成ポリシーを設定できます。 詳細については、次のリンクを参照してください。

  - [Android または iOS デバイスのアプリ保護設定を設定する](app-protection-settings-for-android-and-ios.md)

  - [Windows 10 デバイスのアプリケーション保護設定を設定する](protection-settings-for-windows-10-devices.md)

  - [Pc のデバイス保護設定をWindows 10する](protection-settings-for-windows-10-pcs.md)
  
4. ポリシーを設定すると、ユーザーと従業員は次のデバイスを設定できます。

  - デバイス[の手順については、「Windowsユーザー Microsoft 365 Business Premiumデバイス](set-up-windows-devices.md)をセットアップする」をWindowsしてください。 

  - Android スマートフォンと iPhone[の手順については、「Microsoft 365 Business Premiumユーザー](set-up-mobile-devices.md)向けモバイル デバイスのセットアップ」を参照してください。 
  
### <a name="mailbox-size"></a>メールボックスのサイズ

Microsoft 365 Business Premiumプラン 1 を使用する場合、50 GB のExchange Onlineがあります。 Microsoft 365 Business Premium への移行中に、ユーザーがメールボックス ストレージの 50 GB を超える場合は、このユーザーに Exchange Online プラン 2 を割り当て、両方を割り当てるのは不可能な Exchange Online プラン 1 を削除してください。

### <a name="threat-protection"></a>脅威に対する保護

サーバーに移行した後Microsoft 365 Business Premium、ユーザーに対して Defender をOffice 365。 概要[については、「Microsoft Defender for Office 365」](../security/office-365-security/defender-for-office-365.md)を参照してください。 セットアップするには、「セーフ[リンクのセットアップ、](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)添付ファイルのセーフ、および Defender for Office 365 でのフィッシング対策[](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)[のセットアップ」を参照してください](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)。

### <a name="sensitivity-labels"></a>秘密度ラベル

感度ラベルの使用を開始するには、「感度ラベルの概要 [」と](../compliance/sensitivity-labels.md) 「感度ラベルの作成と管理」 [ビデオを参照](../business-video/create-sensitivity-labels.md) してください。

## <a name="related-content"></a>関連コンテンツ

[手動でプランを変更](../commerce/subscriptions/change-plans-manually.md) する (記事)\
[デバイスWindows (ビデオ) Windows 10 Pro](upgrade-to-windows-pro-creators-update.md)アップグレードする
[Android または iOS デバイスのアプリ保護設定を設定](app-protection-settings-for-android-and-ios.md) する (記事)\
[デバイスのアプリケーション保護設定を設定または編集Windows 10 (](protection-settings-for-windows-10-devices.md)記事)\
[]

