---
title: Microsoft 365 Business への移行 (Office 365 E3 から)
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: cb70260201686cae02428c715ac98ffe2f88787f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198099"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="e8b15-103">365 E3 Office Microsoft 365 Business Premium への移行</span><span class="sxs-lookup"><span data-stu-id="e8b15-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="e8b15-104">Microsoft 365 Business Premium には、クラス最高のクラウドベースの生産性アプリと簡単なデバイス管理とセキュリティを組み合わせた、小規模ビジネスに必要なすべてが含されています。</span><span class="sxs-lookup"><span data-stu-id="e8b15-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="e8b15-105">現在、Office 365 E3 サブスクリプションをお持ちで、従業員数が 300 人を超える場合は、セキュリティ機能を追加するために Microsoft 365 Business Premium への切り替えをご検討ください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="e8b15-106">移行は簡単です。最初にライセンスを切り替えて、現在のサブスクリプション内のすべてのデータとユーザー情報が維持されます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="e8b15-107">移行後、Microsoft 365 Business Premium で追加される機能をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8b15-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="e8b15-108">365 E3 Office Microsoft 365 Business Premium の違い</span><span class="sxs-lookup"><span data-stu-id="e8b15-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="e8b15-109">次の表に、Microsoft 365 Business Premium と 365 E3 Officeを示します。</span><span class="sxs-lookup"><span data-stu-id="e8b15-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="e8b15-110">機能</span><span class="sxs-lookup"><span data-stu-id="e8b15-110">Feature</span></span>    | <span data-ttu-id="e8b15-111">Microsoft 365 Business Premium のサポート</span><span class="sxs-lookup"><span data-stu-id="e8b15-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="e8b15-112">365 E3 Officeサポート</span><span class="sxs-lookup"><span data-stu-id="e8b15-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="e8b15-113">**社内**</span><span class="sxs-lookup"><span data-stu-id="e8b15-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="e8b15-114">Officeアプリ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e8b15-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="e8b15-115">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="e8b15-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="e8b15-116">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="e8b15-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="e8b15-117">**クラウド生産性アプリ**</span><span class="sxs-lookup"><span data-stu-id="e8b15-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="e8b15-118">Exchange Online と Outlook</span><span class="sxs-lookup"><span data-stu-id="e8b15-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="e8b15-119">メールボックスあたり 50 GB のストレージ制限と無制限のストレージExchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="e8b15-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="e8b15-120">メールボックスあたり 100 GB のストレージ制限と無制限のストレージExchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="e8b15-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="e8b15-121">Teams</span><span class="sxs-lookup"><span data-stu-id="e8b15-121">Teams</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png) | 
| <span data-ttu-id="e8b15-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e8b15-124">OneDrive for Business</span></span>    | <span data-ttu-id="e8b15-125">ユーザーあたり 1 TB のストレージ制限</span><span class="sxs-lookup"><span data-stu-id="e8b15-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="e8b15-126">無制限</span><span class="sxs-lookup"><span data-stu-id="e8b15-126">Unlimited</span></span> | 
| <span data-ttu-id="e8b15-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="e8b15-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png) | 
| <span data-ttu-id="e8b15-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="e8b15-130">StaffHub</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png) | 
| <span data-ttu-id="e8b15-133">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="e8b15-133">Outlook Customer Manager</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | | 
| <span data-ttu-id="e8b15-135">**脅威の防止**</span><span class="sxs-lookup"><span data-stu-id="e8b15-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="e8b15-136">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="e8b15-136">Defender for Office 365 Plan 1</span></span> | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | <span data-ttu-id="e8b15-138">含まれていませんが、追加できます</span><span class="sxs-lookup"><span data-stu-id="e8b15-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="e8b15-139">**ID 管理**</span><span class="sxs-lookup"><span data-stu-id="e8b15-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="e8b15-140">ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービス パスワードリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス ID のパスワード ライトバック</span><span class="sxs-lookup"><span data-stu-id="e8b15-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    |  | 
| <span data-ttu-id="e8b15-142">**デバイスおよびアプリの管理**</span><span class="sxs-lookup"><span data-stu-id="e8b15-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="e8b15-143">Microsoft Intune、Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="e8b15-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    |  |
| <span data-ttu-id="e8b15-145">共有コンピューターのライセンス認証</span><span class="sxs-lookup"><span data-stu-id="e8b15-145">Shared computer activation</span></span>|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![365 E3 Office付属](../media/check-mark.png)| 
| <span data-ttu-id="e8b15-148">Win 7/8.1 Pro ライセンスから Windows 10 Pro へのアップグレード権限</span><span class="sxs-lookup"><span data-stu-id="e8b15-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    || 
| <span data-ttu-id="e8b15-150">**情報保護**</span><span class="sxs-lookup"><span data-stu-id="e8b15-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="e8b15-151">Office 365 データ損失防止</span><span class="sxs-lookup"><span data-stu-id="e8b15-151">Office 365 Data Loss Prevention</span></span>|    ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)|![365 E3 Office付属](../media/check-mark.png)|
|<span data-ttu-id="e8b15-154">Azure Information Protection Plan 1, Bitlocker の適用</span><span class="sxs-lookup"><span data-stu-id="e8b15-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)||
|<span data-ttu-id="e8b15-156">Azure Information Protection Plan 1, Sensitivity labels</span><span class="sxs-lookup"><span data-stu-id="e8b15-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)||
|<span data-ttu-id="e8b15-158">**クライアント アクセス ライセンス (CAL 権限)**</span><span class="sxs-lookup"><span data-stu-id="e8b15-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="e8b15-159">エンタープライズ CAL スイート (Exchange、SharePoint、Skype)</span><span class="sxs-lookup"><span data-stu-id="e8b15-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![365 E3 Office付属](../media/check-mark.png)|

<span data-ttu-id="e8b15-161"><sup>1</sup> microsoft 365 Business Premium バージョンの Office アプリには、グループ ポリシー、アプリの利用統計情報、更新コントロール、スプレッドシートの比較と照会、またはビジネス インテリジェンスによるボリュームライセンス認証は含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8b15-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="e8b15-162">移行</span><span class="sxs-lookup"><span data-stu-id="e8b15-162">Migration</span></span>

<span data-ttu-id="e8b15-163">サブスクリプションを移行するには、「Microsoft [](../commerce/subscriptions/change-plans-manually.md) 365 Business Premium に少数のユーザーを移動する場合は、手動でプランを変更する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="e8b15-164">また、すべてのユーザー [を自動的](../commerce/subscriptions/upgrade-to-different-plan.md)にアップグレードしたり、パートナーと一緒に E3 サブスクリプションとライセンスを Microsoft 365 Business Premium サブスクリプションに移行したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="e8b15-165">次のセクションでは、必要な変更がある場合は変更し、移行後に実行できる操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8b15-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="e8b15-166">Office 365 E3 サブスクリプションの構成とデータ</span><span class="sxs-lookup"><span data-stu-id="e8b15-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="e8b15-167">移行する前に、現在のサブスクリプションまたはデータに変更を加える必要は一切ない。これには次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="e8b15-168">DNS レコードやドメイン名などのサブスクリプション構成。</span><span class="sxs-lookup"><span data-stu-id="e8b15-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="e8b15-169">多要素認証や条件付きアクセス ポリシーなどのユーザー アカウントとグループ アカウントと認証設定。</span><span class="sxs-lookup"><span data-stu-id="e8b15-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="e8b15-170">生産性サービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。</span><span class="sxs-lookup"><span data-stu-id="e8b15-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="e8b15-171">Officeアプリケーションは自動的に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-171">Office applications will scale automatically.</span></span> <span data-ttu-id="e8b15-172">Office 365 モダン ライセンスは、72 時間ごとにユーザーのライセンス割り当てを確認し、Office アプリケーションをユーザー サブスクリプションに一致するバージョンに変換します。</span><span class="sxs-lookup"><span data-stu-id="e8b15-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="e8b15-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e8b15-173">Windows 10</span></span>

<span data-ttu-id="e8b15-174">Windows が Windows Pro Creator 更新プログラムにまだインストールされていない場合は [、Windows Pro Creators Update にアップグレードします](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="e8b15-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="e8b15-175">ユーザーデバイスとファイルを保護するためのポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="e8b15-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="e8b15-176">365 MDM Officeデバイスをセットアップすると、それらのデバイスは Microsoft 365 管理センターの [デバイス] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e8b15-177">設定したポリシーは、Intune ポータルのクラシック ポリシーの一覧に [表示されます](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)。</span><span class="sxs-lookup"><span data-stu-id="e8b15-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="e8b15-178">Microsoft 365 Business Premium にライセンスを割り当てた後、ユーザーのデバイスとファイルの保護を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="e8b15-179">組織内のすべてのユーザーを Microsoft 365 Business Premium にアップグレードした場合は、ホーム ページにセットアップ ウィザードが表示され、セットアップ ウィザードの手順で [[Microsoft 365 Business Premium](set-up.md) のセットアップ] に従ってファイルとモバイル デバイスを保護できます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="e8b15-180">[デバイス] ページで、次の手順を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="e8b15-181">管理センターの左側のナビゲーションで、[デバイス ポリシー]  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e8b15-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="e8b15-182">[デバイス ポリシー **] ページで、[** 追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8b15-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="e8b15-183">[ポリシー **の追加]** ウィンドウでポリシーに名前を付け、ドロップダウンから **[ポリシー** の種類] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8b15-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="e8b15-184">Android デバイスと iPhone デバイス、および Windows 10 でファイルを保護するためのアプリケーション ポリシーを設定し、会社所有の Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="e8b15-185">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="e8b15-186">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="e8b15-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="e8b15-187">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="e8b15-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="e8b15-188">Windows 10 PC のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="e8b15-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="e8b15-189">ポリシーを設定すると、ユーザーと従業員は次のデバイスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e8b15-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="e8b15-190">Windows [デバイスの手順については、「Microsoft 365 Business Premium](set-up-windows-devices.md) ユーザー向け Windows デバイスのセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="e8b15-191">Android スマートフォンと iPhone [の手順については、「Microsoft 365 Business Premium](set-up-mobile-devices.md) ユーザー用のモバイル デバイスをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="e8b15-192">メールボックスのサイズ</span><span class="sxs-lookup"><span data-stu-id="e8b15-192">Mailbox Size</span></span>

<span data-ttu-id="e8b15-193">Microsoft 365 Business Premium には、Exchange Online プラン 1 を使用する 50 GB のストレージ制限があります。</span><span class="sxs-lookup"><span data-stu-id="e8b15-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="e8b15-194">Microsoft 365 Business Premium への移行中に、ユーザーがメールボックス ストレージの 50 GB を超える場合は、このユーザーに Exchange Online プラン 2 を割り当て、両方を割り当てるのは不可能な Exchange Online プラン 1 を削除してください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="e8b15-195">脅威に対する保護</span><span class="sxs-lookup"><span data-stu-id="e8b15-195">Threat protection</span></span>

<span data-ttu-id="e8b15-196">Microsoft 365 Business Premium に移行した後、365 の Defender Officeがあります。</span><span class="sxs-lookup"><span data-stu-id="e8b15-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="e8b15-197">概要 [については、「Microsoft Defender for Office 365」](../security/office-365-security/defender-for-office-365.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-197">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="e8b15-198">セットアップするには、「[安全なリンク](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)の設定、安全[](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)な添付ファイルのセットアップ、および[365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)の Defender でのフィッシング対策のOfficeしてください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="e8b15-199">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="e8b15-199">Sensitivity labels</span></span>

<span data-ttu-id="e8b15-200">感度ラベルの使用を開始するには、「感度ラベルの概要 [」と](../compliance/sensitivity-labels.md) 「感度ラベルの作成と管理」 [ビデオを参照](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) してください。</span><span class="sxs-lookup"><span data-stu-id="e8b15-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
