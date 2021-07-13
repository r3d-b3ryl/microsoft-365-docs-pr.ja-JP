---
title: ビジネス向け Azure AD参加デバイスからオンプレミス リソースにMicrosoft 365する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: ビジネス アプリの回線、ファイル共有、プリンターなど、オンプレミスのリソースにアクセスする方法について、Azure Active DirectoryデバイスWindows 10します。
ms.openlocfilehash: 71d60e0187c917dffb7390afcedf22dc73f44008
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393461"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="1aa1a-103">Azure に参加しているデバイスからオンプレミスADにアクセスMicrosoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1aa1a-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="1aa1a-104">この記事は、このMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="1aa1a-105">参加Windows 10デバイスAzure Active Directory、Microsoft 365 アプリなど、すべてのクラウドベースのリソースにアクセスできます。Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="1aa1a-106">また、業務 (LOB) アプリ、ファイル共有、プリンターなど、オンプレミスのリソースへのアクセスを許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="1aa1a-107">アクセスを許可するには[、Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect)を使用して、オンプレミスの Active Directory と同期Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span>

<span data-ttu-id="1aa1a-108">詳細については、「デバイス管理の概要」を参照[Azure Active Directory。](/azure/active-directory/device-management-introduction)</span><span class="sxs-lookup"><span data-stu-id="1aa1a-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="1aa1a-109">手順は、次のセクションでも要約されています。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-109">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="1aa1a-110">Azure の実行AD Connect</span><span class="sxs-lookup"><span data-stu-id="1aa1a-110">Run Azure AD Connect</span></span>

<span data-ttu-id="1aa1a-111">以下の手順を実行して、組織の Azure ADに参加しているデバイスがオンプレミス のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>

1. <span data-ttu-id="1aa1a-112">ローカル Active Directory から Azure Active Directory にユーザー、グループ、連絡先を同期するには、「ディレクトリ同期のセットアップ」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect[を](../enterprise/set-up-directory-synchronization.md)実行Office 365。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>

2. <span data-ttu-id="1aa1a-113">ディレクトリ同期が完了したら、組織のデバイスが Azure Windows 10参加ADしてください。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="1aa1a-114">この手順は、デバイスごとに個別Windows 10されます。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="1aa1a-115">詳細[については、「ユーザー WindowsデバイスをMicrosoft 365 Business Premiumする」](set-up-windows-devices.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span>

3. <span data-ttu-id="1aa1a-116">デバイスが Azure Windows 10参加ADしたら、各ユーザーはデバイスを再起動し、ユーザーの資格情報を使用Microsoft 365 Business Premium必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="1aa1a-117">これで、すべてのデバイスがオンプレミスのリソースにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-117">All devices now have access to on-premises resources as well.</span></span>

<span data-ttu-id="1aa1a-118">Azure に参加しているデバイスのオンプレミス リソースにアクセスするには、追加AD必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="1aa1a-119">この機能は、Windows 10。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-119">This functionality is built into Windows 10.</span></span>

<span data-ttu-id="1aa1a-120">パスワード以外の AADJ デバイスにログインする予定がある場合 WHFB 資格情報ログインを介して PIN/Bio-metric のようにし、オンプレミスのリソース (共有、プリンターなど)[](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)にアクセスする場合は、この記事に従います。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares, printers, etc.), please follow [this article](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base).</span></span>

<span data-ttu-id="1aa1a-121">組織が上記の Azure AD参加デバイス構成に展開する準備ができていない場合は、ハイブリッド Azure AD [参加デバイス構成のセットアップを検討してください](manage-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="1aa1a-122">Azure デバイスにデバイスをWindowsする際の考慮事項AD</span><span class="sxs-lookup"><span data-stu-id="1aa1a-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="1aa1a-123">Azure-Windows参加しているADが以前にドメインに参加しているか、ワークグループに参加している場合は、次の制限を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>

- <span data-ttu-id="1aa1a-124">デバイス Azure が参加AD、既存のプロファイルを参照せずに新しいユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="1aa1a-125">プロファイルは手動で移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="1aa1a-126">ユーザー プロファイルには、お気に入り、ローカル ファイル、ブラウザー設定、およびユーザー設定スタート メニュー含まれる。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="1aa1a-127">最適な方法は、既存のファイルと設定を新しいプロファイルにマップするサード パーティ製のツールを見つける方法です。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="1aa1a-128">デバイスがグループ ポリシー オブジェクト (GPO) を使用している場合、一部の GPO には Intune で同等の [構成](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) サービス プロバイダー (CSP) が含されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="1aa1a-129">[MMAT ツールを実行して](https://www.microsoft.com/download/details.aspx?id=45520)、既存の GPO に対応する CSP を検索します。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="1aa1a-130">ユーザーが Active Directory 認証に依存するアプリケーションに対して認証できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="1aa1a-131">従来のアプリを評価し、可能であれば最新の Auth を使用するアプリへの更新を検討します。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="1aa1a-132">Active Directory プリンターの検出が機能しません。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="1aa1a-133">すべてのユーザーに直接プリンター パスを指定するか、ユニバーサル 印刷 [を使用できます](/universal-print/)。</span><span class="sxs-lookup"><span data-stu-id="1aa1a-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>

### <a name="related-articles"></a><span data-ttu-id="1aa1a-134">関連記事</span><span class="sxs-lookup"><span data-stu-id="1aa1a-134">Related Articles</span></span>

[<span data-ttu-id="1aa1a-135">Azure サーバーの前提条件AD Connect</span><span class="sxs-lookup"><span data-stu-id="1aa1a-135">Prerequisites for Azure AD Connect</span></span>](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
