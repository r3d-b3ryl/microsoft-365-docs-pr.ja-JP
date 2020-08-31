---
title: Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory に参加している Windows 10 デバイスから、基幹業務アプリケーション、ファイル共有、プリンターなどのオンプレミスのリソースにアクセスする方法について説明します。
ms.openlocfilehash: 9b83781afee746b06bbdf90962de0f55ffbcb118
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307495"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="81909-103">Microsoft 365 Business Premium の Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="81909-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="81909-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="81909-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="81909-105">Azure Active Directory に参加している Windows 10 デバイスはすべて、Microsoft 365 アプリなどのクラウドベースのすべてのリソースにアクセスでき、Microsoft 365 Business Premium で保護することができます。</span><span class="sxs-lookup"><span data-stu-id="81909-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="81909-106">基幹業務 (LOB) アプリ、ファイル共有、プリンターなどの社内リソースへのアクセスを許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="81909-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="81909-107">アクセスを許可するには、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) を使用してオンプレミスの active Directory を Azure active directory と同期します。</span><span class="sxs-lookup"><span data-stu-id="81909-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="81909-108">詳細については、「 [Azure Active Directory でのデバイス管理の概要](https://docs.microsoft.com/azure/active-directory/device-management-introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81909-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="81909-109">手順の概要についても、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="81909-109">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81909-110">この手順は、OAuth および NTLM にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="81909-110">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="81909-111">Kerberos はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81909-111">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="81909-112">Azure AD Connect を実行する</span><span class="sxs-lookup"><span data-stu-id="81909-112">Run Azure AD Connect</span></span>

<span data-ttu-id="81909-113">次の手順を実行して、組織の Azure AD に参加しているデバイスがオンプレミスのリソースにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="81909-113">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="81909-114">ユーザー、グループ、および連絡先をローカルの Active Directory から Azure Active Directory に同期するには、「 [Set up Directory synchronization For Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect を実行します。</span><span class="sxs-lookup"><span data-stu-id="81909-114">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="81909-115">ディレクトリ同期が完了したら、組織の Windows 10 デバイスが Azure AD に参加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="81909-115">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="81909-116">この手順は、各 Windows 10 デバイスで個別に実行します。</span><span class="sxs-lookup"><span data-stu-id="81909-116">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="81909-117">詳細については、「 [Microsoft 365 Business Premium ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81909-117">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="81909-118">Windows 10 デバイスが Azure AD に参加している場合、各ユーザーはデバイスを再起動して、Microsoft 365 Business Premium の資格情報でサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81909-118">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="81909-119">これで、すべてのデバイスがオンプレミスのリソースにもアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="81909-119">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="81909-120">Azure AD に参加しているデバイスのオンプレミスのリソースにアクセスするために、追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="81909-120">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="81909-121">この機能は、Windows 10 に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="81909-121">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="81909-122">[PIN/Bio] のように、パスワード以外の方法で、(WHFB credential ログイン経由で) AADJ デバイスにログインし、オンプレミスのリソース (共有、プリンター) にアクセスする予定がある場合。など)。 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="81909-122">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="81909-123">前述の Azure AD に参加しているデバイス構成に組織が展開する準備ができていない場合は、 [ハイブリッド AZURE ad の参加](manage-windows-devices.md)しているデバイス構成を設定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="81909-123">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="81909-124">Windows デバイスを Azure AD に参加させる際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="81909-124">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="81909-125">Azure AD に参加している Windows デバイスが以前にドメインに参加しているか、ワークグループに参加していた場合は、次の制限事項を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="81909-125">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="81909-126">デバイス Azure AD が参加すると、既存のプロファイルを参照せずに新しいユーザーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="81909-126">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="81909-127">プロファイルは手動で移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81909-127">Profiles must be manually migrated.</span></span> <span data-ttu-id="81909-128">ユーザープロファイルには、お気に入り、ローカルファイル、ブラウザーの設定、および [スタート] メニューの設定などの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81909-128">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="81909-129">最善の方法は、既存のファイルと設定を新しいプロファイルにマップするためのサードパーティ製ツールを検索することです。</span><span class="sxs-lookup"><span data-stu-id="81909-129">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="81909-130">デバイスがグループポリシーオブジェクト (GPO) を使用している場合、一部の Gpo には Intune での同等の [構成サービスプロバイダー](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) が含まれていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="81909-130">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="81909-131">[Mmat ツール](https://www.microsoft.com/download/details.aspx?id=45520)を実行して、既存の gpo の同等の csp を検索します。</span><span class="sxs-lookup"><span data-stu-id="81909-131">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="81909-132">ユーザーは、Active Directory 認証に依存するアプリケーションに対して認証を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="81909-132">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="81909-133">レガシアプリを評価し、可能であればモダン認証を使用するアプリに更新することを検討します。</span><span class="sxs-lookup"><span data-stu-id="81909-133">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="81909-134">Active Directory プリンターの検出は機能しません。</span><span class="sxs-lookup"><span data-stu-id="81909-134">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="81909-135">すべてのユーザーに直接のプリンターパスを提供したり、 [ハイブリッドクラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="81909-135">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
