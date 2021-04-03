---
title: Microsoft 365 Business への移行 (Office 365 E3 から)
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
search.appverid:
- BCS160
- MET150
description: 365 E3 から Microsoft 365 Business Premium にビジネスを移行するOffice説明します。
ms.openlocfilehash: ffb82fa40f05383260ac1b97ed0bdf5f2f30c1df
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578329"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>365 E3 Office Microsoft 365 Business Premium への移行

Microsoft 365 Business Premium には、クラス最高のクラウドベースの生産性アプリと簡単なデバイス管理とセキュリティを組み合わせた、小規模ビジネスに必要なすべてが含されています。 現在、Office 365 E3 サブスクリプションをお持ちで、従業員数が 300 人を超える場合は、セキュリティ機能を追加するために Microsoft 365 Business Premium への切り替えをご検討ください。

移行は簡単です。最初にライセンスを切り替えて、現在のサブスクリプション内のすべてのデータとユーザー情報が維持されます。 移行後、Microsoft 365 Business Premium で追加される機能をセットアップする必要があります。

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>365 E3 Office Microsoft 365 Business Premium の違い

次の表に、Microsoft 365 Business Premium と 365 E3 Officeを示します。

| 機能    | Microsoft 365 Business Premium のサポート    | 365 E3 Officeサポート | 
|:-------|:-----|:-----|
| **社内**        | | | 
| Officeアプリ<sup>1</sup>    | Microsoft 365 Apps for business    | Microsoft 365 Apps for enterprise | 
| **クラウド生産性アプリ**        | | | 
| Exchange Online と Outlook    | メールボックスあたり 50 GB のストレージ制限と無制限のストレージExchange Online Archiving    | メールボックスあたり 100 GB のストレージ制限と無制限のストレージExchange Online Archiving | 
| Teams    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png) | 
| OneDrive for Business    | ユーザーあたり 1 TB のストレージ制限    | 無制限 | 
| Yammer, SharePoint Online, Planner, Stream    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png) | 
| StaffHub    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png) | 
| Outlook Customer Manager    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | | 
| **脅威の防止**        | | | 
| Microsoft Defender for Office 365 プラン 1 | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | 含まれていませんが、追加できます | 
| **ID 管理**        | | | 
| ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービス パスワードリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス ID のパスワード ライトバック|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    |  | 
| **デバイスおよびアプリの管理**        | | |
| Microsoft Intune、Windows AutoPilot|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    |  |
| 共有コンピューターのライセンス認証|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png)| 
| Win 7/8.1 Pro ライセンスから Windows 10 Pro へのアップグレード権限|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    || 
| **情報保護**        | | |
|Office 365 データ損失防止|    ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)|![365 E3 Office付属](../media/check-mark.png)|
|Azure Information Protection Plan 1, Bitlocker の適用|![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)||
|Azure Information Protection Plan 1, Sensitivity labels|![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)||
|**クライアント アクセス ライセンス (CAL 権限)**|||
|エンタープライズ CAL スイート (Exchange、SharePoint、Skype)||![365 E3 Office付属](../media/check-mark.png)|

<sup>1</sup> microsoft 365 Business Premium バージョンの Office アプリには、グループ ポリシー、アプリの利用統計情報、更新コントロール、スプレッドシートの比較と照会、またはビジネス インテリジェンスによるボリュームライセンス認証は含まれています。

## <a name="migration"></a>移行

サブスクリプションを移行するには、「Microsoft [](../commerce/subscriptions/change-plans-manually.md) 365 Business Premium に少数のユーザーを移動する場合は、手動でプランを変更する」を参照してください。 また、すべてのユーザー [を自動的](../commerce/subscriptions/upgrade-to-different-plan.md)にアップグレードしたり、パートナーと一緒に E3 サブスクリプションとライセンスを Microsoft 365 Business Premium サブスクリプションに移行したりすることもできます。
次のセクションでは、必要な変更がある場合は変更し、移行後に実行できる操作について説明します。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 サブスクリプションの構成とデータ
移行する前に、現在のサブスクリプションまたはデータに変更を加える必要は一切ない。これには次の内容が含まれます。

- DNS レコードやドメイン名などのサブスクリプション構成。
- 多要素認証や条件付きアクセス ポリシーなどのユーザー アカウントとグループ アカウントと認証設定。
- 生産性サービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。
- Officeアプリケーションは自動的に拡張されます。 Office 365 モダン ライセンスは、72 時間ごとにユーザーのライセンス割り当てを確認し、Office アプリケーションをユーザー サブスクリプションに一致するバージョンに変換します。

### <a name="windows-10"></a>Windows 10

Windows が Windows Pro Creator 更新プログラムにまだインストールされていない場合は [、Windows Pro Creators Update にアップグレードします](upgrade-to-windows-pro-creators-update.md)。

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>ユーザーデバイスとファイルを保護するためのポリシーの設定

> [!NOTE]
> 365 MDM Officeデバイスをセットアップすると、それらのデバイスは Microsoft 365 管理センターの [デバイス] ページに表示されます。 設定したポリシーは、Intune ポータルのクラシック ポリシーの一覧に [表示されます](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)。

Microsoft 365 Business Premium にライセンスを割り当てた後、ユーザーのデバイスとファイルの保護を開始できます。

組織内のすべてのユーザーを Microsoft 365 Business Premium にアップグレードした場合は、ホーム ページにセットアップ ウィザードが表示され、セットアップ ウィザードの手順で [[Microsoft 365 Business Premium](set-up.md) のセットアップ] に従ってファイルとモバイル デバイスを保護できます。

[デバイス] ページで、次の手順を実行することもできます。
  
1. 管理センターの左側のナビゲーションで、[デバイス ポリシー]  \> **に移動します**。
    
2. [デバイス ポリシー **] ページで、[** 追加] を **選択します**。
    
3. [ポリシー **の追加]** ウィンドウでポリシーに名前を付け、ドロップダウンから **[ポリシー** の種類] を選択します。 
    
     Android デバイスと iPhone デバイス、および Windows 10 でファイルを保護するためのアプリケーション ポリシーを設定し、会社所有の Windows 10 デバイスのデバイス構成ポリシーを設定できます。 詳細については、次のリンクを参照してください。
    
  - [Android または iOS デバイスのアプリ保護設定を設定する](app-protection-settings-for-android-and-ios.md)
    
  - [Windows 10 デバイスのアプリケーション保護設定を設定する](protection-settings-for-windows-10-devices.md)
    
  - [Windows 10 PC のデバイス保護設定を設定する](protection-settings-for-windows-10-pcs.md)
  
4. ポリシーを設定すると、ユーザーと従業員は次のデバイスを設定できます。
    
  - Windows [デバイスの手順については、「Microsoft 365 Business Premium](set-up-windows-devices.md) ユーザー向け Windows デバイスのセットアップ」を参照してください。 
    
  - Android スマートフォンと iPhone [の手順については、「Microsoft 365 Business Premium](set-up-mobile-devices.md) ユーザー用のモバイル デバイスをセットアップする」を参照してください。 
  
### <a name="mailbox-size"></a>メールボックスのサイズ

Microsoft 365 Business Premium には、Exchange Online プラン 1 を使用する 50 GB のストレージ制限があります。 Microsoft 365 Business Premium への移行中に、ユーザーがメールボックス ストレージの 50 GB を超える場合は、このユーザーに Exchange Online プラン 2 を割り当て、両方を割り当てるのは不可能な Exchange Online プラン 1 を削除してください。


### <a name="threat-protection"></a>脅威に対する保護

Microsoft 365 Business Premium に移行した後、365 の Defender Officeがあります。 概要 [については、「Microsoft Defender for Office 365」](../security/office-365-security/defender-for-office-365.md) を参照してください。 セットアップするには、「[安全なリンク](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)の設定、安全[](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)な添付ファイルのセットアップ、および[365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)の Defender でのフィッシング対策のOfficeしてください。

### <a name="sensitivity-labels"></a>秘密度ラベル

感度ラベルの使用を開始するには、「感度ラベルの概要 [」と](../compliance/sensitivity-labels.md) 「感度ラベルの作成と管理」 [ビデオを参照](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) してください。
