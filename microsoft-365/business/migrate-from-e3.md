---
title: Office 365 E3 からの Microsoft 365 Business への移行
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
search.appverid:
- BCS160
- MET150
description: Office 365 E3 から、ビジネスを Microsoft 365 Business に移行する方法について説明します。
ms.openlocfilehash: 5142038110cada6e1da77d405c82f119e0f9e4d3
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002436"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="b5cfe-103">Office 365 E3 から Microsoft 365 Business への移行</span><span class="sxs-lookup"><span data-stu-id="b5cfe-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="b5cfe-104">Microsoft 365 Business は、お客様の中小企業に必要なすべての機能を備えており、クラスを備えたクラウドベースの生産性向上アプリをシンプルなデバイス管理とセキュリティと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span>  <span data-ttu-id="b5cfe-105">現在、Office 365 E3 サブスクリプションを所有していて、従業員の数が300を超える場合は、追加のセキュリティ機能を使用するように Microsoft 365 Business に切り替えることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-105">If you currently have an Office 365 E3 subscription, but don’t have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="b5cfe-106">移行は簡単です。最初にライセンスを切り替え、現在のサブスクリプションのすべてのデータとユーザー情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="b5cfe-107">移行後に、Microsoft 365 Business に追加された機能を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-107">After the migration you will need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="b5cfe-108">Office 365 E3 と Microsoft 365 Business の相違点</span><span class="sxs-lookup"><span data-stu-id="b5cfe-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="b5cfe-109">次の表は、Microsoft 365 Business と Office 365 E3 の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="b5cfe-110">機能</span><span class="sxs-lookup"><span data-stu-id="b5cfe-110">Feature</span></span>   | <span data-ttu-id="b5cfe-111">Microsoft 365 Business でのサポート</span><span class="sxs-lookup"><span data-stu-id="b5cfe-111">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="b5cfe-112">Office 365 E3 のサポート</span><span class="sxs-lookup"><span data-stu-id="b5cfe-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="b5cfe-113">**社内**</span><span class="sxs-lookup"><span data-stu-id="b5cfe-113">**On-premises**</span></span>       | | | 
| <span data-ttu-id="b5cfe-114">Office アプリ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b5cfe-114">Office apps<sup>1</sup></span></span>   | <span data-ttu-id="b5cfe-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="b5cfe-115">Office 365 Business</span></span>   | <span data-ttu-id="b5cfe-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="b5cfe-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="b5cfe-117">**クラウド生産性アプリ**</span><span class="sxs-lookup"><span data-stu-id="b5cfe-117">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="b5cfe-118">Exchange Online および Outlook</span><span class="sxs-lookup"><span data-stu-id="b5cfe-118">Exchange Online and Outlook</span></span>   | <span data-ttu-id="b5cfe-119">メールボックスごとに 50 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="b5cfe-119">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="b5cfe-120">メールボックスごとに 100 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="b5cfe-120">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="b5cfe-121">Teams</span><span class="sxs-lookup"><span data-stu-id="b5cfe-121">Teams</span></span> | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Office 365 E3 に含まれている](./media/check-mark.png) | 
| <span data-ttu-id="b5cfe-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b5cfe-124">OneDrive for Business</span></span> | <span data-ttu-id="b5cfe-125">ユーザーごとに 1 TB のストレージ制限</span><span class="sxs-lookup"><span data-stu-id="b5cfe-125">1 TB storage limit per user</span></span>   | <span data-ttu-id="b5cfe-126">無制限</span><span class="sxs-lookup"><span data-stu-id="b5cfe-126">Unlimited</span></span> | 
| <span data-ttu-id="b5cfe-127">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="b5cfe-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Office 365 E3 に含まれている](./media/check-mark.png) | 
| <span data-ttu-id="b5cfe-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="b5cfe-130">StaffHub</span></span>  | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Office 365 E3 に含まれている](./media/check-mark.png) | 
| <span data-ttu-id="b5cfe-133">Outlook カスタマーマネージャー、ミル Eiq</span><span class="sxs-lookup"><span data-stu-id="b5cfe-133">Outlook Customer Manager, MileIQ</span></span>  | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | | 
| <span data-ttu-id="b5cfe-135">**脅威保護**</span><span class="sxs-lookup"><span data-stu-id="b5cfe-135">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="b5cfe-136">Office 365 Advanced Threat Protection (ATP) プラン1</span><span class="sxs-lookup"><span data-stu-id="b5cfe-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Microsoft 365 Business に含まれている](./media/check-mark.png)  | <span data-ttu-id="b5cfe-138">含まれていませんが、に追加できます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="b5cfe-139">**ID 管理**</span><span class="sxs-lookup"><span data-stu-id="b5cfe-139">**Identity management**</span></span>       | | | 
| <span data-ttu-id="b5cfe-140">ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービスによるパスワードのリセット、Azure 多要素認証 (MFA)、条件付きアクセス、オンプレミス id のパスワードの書き戻し</span><span class="sxs-lookup"><span data-stu-id="b5cfe-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Microsoft 365 Business に含まれている](./media/check-mark.png) |  | 
| <span data-ttu-id="b5cfe-142">**デバイスとアプリの管理**</span><span class="sxs-lookup"><span data-stu-id="b5cfe-142">**Device and app management**</span></span>     | | |
| <span data-ttu-id="b5cfe-143">Microsoft Intune、Windows 自動操縦</span><span class="sxs-lookup"><span data-stu-id="b5cfe-143">Microsoft Intune, Windows AutoPilot</span></span>|  ![Microsoft 365 Business に含まれている](./media/check-mark.png) |  |
| <span data-ttu-id="b5cfe-145">共有コンピューターのライセンス認証</span><span class="sxs-lookup"><span data-stu-id="b5cfe-145">Shared computer activation</span></span>|   ![Microsoft 365 Business に含まれている](./media/check-mark.png) | ![Office 365 E3 に含まれている](./media/check-mark.png)| 
| <span data-ttu-id="b5cfe-148">Win 7/8.1 Pro ライセンスから Windows 10 Pro へのアップグレード権限</span><span class="sxs-lookup"><span data-stu-id="b5cfe-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Microsoft 365 Business に含まれている](./media/check-mark.png) || 
| <span data-ttu-id="b5cfe-150">**情報保護**</span><span class="sxs-lookup"><span data-stu-id="b5cfe-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="b5cfe-151">Office 365 データ損失防止</span><span class="sxs-lookup"><span data-stu-id="b5cfe-151">Office 365 Data Loss Prevention</span></span>|   ![Microsoft 365 Business に含まれている](./media/check-mark.png)|![Office 365 E3 に含まれている](./media/check-mark.png)|
|<span data-ttu-id="b5cfe-154">Azure Information Protection プラン1、Bitlocker 強制</span><span class="sxs-lookup"><span data-stu-id="b5cfe-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Microsoft 365 Business に含まれている](./media/check-mark.png)||
|<span data-ttu-id="b5cfe-156">Azure Information Protection プラン1、機密ラベル</span><span class="sxs-lookup"><span data-stu-id="b5cfe-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Microsoft 365 Business に含まれている](./media/check-mark.png)||
|<span data-ttu-id="b5cfe-158">**クライアントアクセスライセンス (CAL 権限)**</span><span class="sxs-lookup"><span data-stu-id="b5cfe-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="b5cfe-159">エンタープライズ CAL スイート (Exchange、SharePoint、Skype)</span><span class="sxs-lookup"><span data-stu-id="b5cfe-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Office 365 E3 に含まれている](./media/check-mark.png)|

<span data-ttu-id="b5cfe-161"><sup>1</sup> Microsoft 365 Business バージョンの Office アプリには、グループポリシー、アプリテレメトリ、更新制御、スプレッドシートの比較と照会、およびビジネスインテリジェンスによるボリュームライセンス認証は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps do not include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, and business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="b5cfe-162">移行</span><span class="sxs-lookup"><span data-stu-id="b5cfe-162">Migration</span></span>

<span data-ttu-id="b5cfe-163">サブスクリプションを移行するには、「[別のプランに手動で切り替える](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually)」を参照してください。一部のユーザーのみを Microsoft 365 Business に移行する場合は、すべてのユーザーを[自動的にアップグレード](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)するか、パートナーと協力して E3 を移動することができます。Microsoft 365 Business サブスクリプションへのサブスクリプションとライセンス。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-163">To migrate your subscription, see [switch to a different plan manually](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) for instructions if you want to move just a few people to Microsoft 365 Business, you can [upgrade everyone automatically](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), or you can work with partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="b5cfe-164">次のセクションでは、移行後に行う必要のある変更点と、その変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-164">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="b5cfe-165">Office 365 E3 サブスクリプションの構成とデータ</span><span class="sxs-lookup"><span data-stu-id="b5cfe-165">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="b5cfe-166">移行する前に、現在のサブスクリプションまたはデータを変更する必要はありません。これには、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-166">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="b5cfe-167">DNS レコードやドメイン名などのサブスクリプションの構成。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-167">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="b5cfe-168">ユーザーおよびグループのアカウントと、複数要素の認証や条件付きアクセスポリシーなどの認証設定。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-168">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="b5cfe-169">プロダクティビティサービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-169">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="b5cfe-170">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5cfe-170">Windows 10</span></span>

<span data-ttu-id="b5cfe-171">Windows Pro Creator の更新プログラムを適用していない場合は、windows pro Creator update に[アップグレード](upgrade-to-windows-pro-creators-update.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-171">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="b5cfe-172">ユーザーのデバイスとファイルを保護するためのポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="b5cfe-172">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="b5cfe-173">Office 365 MDM ポリシーおよびデバイスをセットアップすると、これらのデバイスは Microsoft 365 管理センターの [**デバイス**] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-173">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b5cfe-174">セットアップしたポリシーはすべて、 [Intune ポータル](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)の従来のポリシーの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-174">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="b5cfe-175">Microsoft 365 Business にライセンスを割り当てたら、ユーザーのデバイスとファイルの保護を開始できます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-175">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="b5cfe-176">組織内のすべてのユーザーを Microsoft 365 Business にアップグレードした場合は、ホームページに [セットアップウィザード] が表示され、[セットアップウィザードの手順で「Microsoft 365 Business](set-up.md)をセットアップする」の手順に従って、ファイルとモバイルデバイスを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-176">If you upgraded everyone in your organization to Microsoft 365 Business, you will see the set up wizard on teh home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="b5cfe-177">[デバイス] ページでは、次の手順を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-177">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="b5cfe-178">管理センターの左側のナビゲーションで、[**デバイス** \> **ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-178">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="b5cfe-179">[**デバイスポリシー** ] ページで、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-179">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="b5cfe-180">[**ポリシーの追加**] ウィンドウで、ポリシーの名前を指定し、ドロップダウンから**ポリシーの種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-180">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="b5cfe-181">Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-181">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="b5cfe-182">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-182">See the following links for details:</span></span>
    
  - [<span data-ttu-id="b5cfe-183">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="b5cfe-183">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="b5cfe-184">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="b5cfe-184">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="b5cfe-185">Windows 10 Pc のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="b5cfe-185">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="b5cfe-186">ポリシーを設定すると、従業員はデバイスをセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-186">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="b5cfe-187">Windows デバイスの手順については、「 [Microsoft 365 Business ユーザーの windows デバイスをセットアップ](set-up-windows-devices.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-187">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="b5cfe-188">Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-188">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="b5cfe-189">脅威保護</span><span class="sxs-lookup"><span data-stu-id="b5cfe-189">Threat protection</span></span>

<span data-ttu-id="b5cfe-190">Microsoft 365 Business に移行した後、Office 365 ATP を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-190">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="b5cfe-191">概要と設定については、「 [Office 365 atp](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 」を参照してください。 atp の安全な[リンク](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)の設定、 [atp の安全な添付ファイルの設定](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)、 [atp のフィッシング対策の設定](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-191">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview and to set up see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="b5cfe-192">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="b5cfe-192">Sensitivity labels</span></span>

<span data-ttu-id="b5cfe-193">機密ラベルの使用を開始するには、機密ラベル[の概要](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)と、[機密ラベルの作成と管理](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)に関するビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cfe-193">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
