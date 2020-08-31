---
title: ドメイン ユーザーを Microsoft 365 に同期する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: ドメイン制御されたユーザーを Microsoft 365 for business と同期します。
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306451"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="3ba72-103">ドメイン ユーザーを Microsoft 365 に同期する</span><span class="sxs-lookup"><span data-stu-id="3ba72-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="3ba72-104">1. ディレクトリ同期の準備</span><span class="sxs-lookup"><span data-stu-id="3ba72-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="3ba72-105">ローカル Active Directory ドメインからユーザーとコンピューターを同期する前に、「 [Microsoft 365 へのディレクトリ同期の準備](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ba72-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="3ba72-106">特に次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3ba72-106">In particular:</span></span>

   - <span data-ttu-id="3ba72-107">次の属性について、ディレクトリに重複が存在しないことを確認してください。 **mail**、 **ProxyAddresses**、および **userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="3ba72-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="3ba72-108">これらの値は一意である必要があり、重複して削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ba72-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="3ba72-109">各ローカルユーザーアカウントの **userPrincipalName** (UPN) 属性を、ライセンスされた Microsoft 365 ユーザーに対応するプライマリ電子メールアドレスと一致するように構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ba72-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="3ba72-110">例: mary.shelley@contoso.com ではなく*mary@contoso* 、 *mary.shelley@contoso.com*</span><span class="sxs-lookup"><span data-stu-id="3ba72-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="3ba72-111">Active Directory ドメインが、 *.com*または *.org*などのインターネットでルーティング可能なサフィックスの代わりに、*ローカル*ユーザーアカウントの UPN サフィックスではなく、ルーティング可能*ではない*サフィックスで終わっている場合は、「[ディレクトリ同期のために非ルーティングドメインを準備する](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)」で説明されているように、まずローカルユーザーアカウントの UPN サフィックスを調整します。</span><span class="sxs-lookup"><span data-stu-id="3ba72-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="3ba72-112">手順 4 (4) の **実行 IdFix** を使用して、オンプレミスの Active Directory がディレクトリ同期の準備が整っていることを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ba72-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="3ba72-113">2. Azure AD Connect をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="3ba72-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="3ba72-114">ユーザー、グループ、および連絡先をローカルの Active directory から Azure Active Directory に同期するには、Azure Active Directory Connect をインストールし、ディレクトリ同期をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3ba72-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="3ba72-115">管理センターで、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 左側のナビゲーションの [ **セットアップ** の選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ba72-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="3ba72-116">[**サインインとセキュリティ**] で、[**組織のディレクトリからユーザーを同期する] の**下にある [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ba72-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="3ba72-117">[ **組織のディレクトリからユーザーを同期** する] ページで、[ **開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ba72-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="3ba72-118">最初のステップ実行 IdFix ツールで、ディレクトリ同期の準備をします。</span><span class="sxs-lookup"><span data-stu-id="3ba72-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="3ba72-119">ウィザードの手順に従って、Azure AD Connect をダウンロードし、それを使用して、ドメイン制御されたユーザーを Microsoft 365 に同期させます。</span><span class="sxs-lookup"><span data-stu-id="3ba72-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="3ba72-120">詳細については、「 [Microsoft 365 のディレクトリ同期をセットアップ](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ba72-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="3ba72-121">Azure AD Connect のオプションを構成する際には、 **パスワード同期**、 **シームレスなシングルサインオン**、 **パスワード書き戻し** 機能を有効にすることをお勧めします。これは、Microsoft 365 for business でもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3ba72-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="3ba72-122">Azure AD Connect のチェックボックスを超えてパスワードを書き戻しするには、いくつかの追加の手順があります。</span><span class="sxs-lookup"><span data-stu-id="3ba72-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="3ba72-123">詳細については、「 [方法: パスワードの書き戻しを構成](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ba72-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="3ba72-124">ドメインに参加している Windows 10 デバイスも管理する場合は、「 [ドメインに参加している windows 10 デバイスを Microsoft 365 Business Premium で管理されるよう](manage-windows-devices.md) にする」を参照して、ハイブリッド Azure AD Join を設定してください。</span><span class="sxs-lookup"><span data-stu-id="3ba72-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 