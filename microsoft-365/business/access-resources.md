---
title: Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory に参加している Windows 10 デバイスから、基幹業務アプリケーション、ファイル共有、プリンターなどのオンプレミスのリソースにアクセスする方法について説明します。
ms.openlocfilehash: 26ba0ffb64ddce32369002120657456e47ac0c7f
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287357"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="19e0e-103">Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="19e0e-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="19e0e-104">Azure Active Directory に参加している Windows 10 デバイスはすべて、Office 365 アプリなどのクラウドベースのすべてのリソースへのアクセス権を持ち、Microsoft 365 Business で保護することができます。</span><span class="sxs-lookup"><span data-stu-id="19e0e-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="19e0e-105">基幹業務 (LOB) アプリ、ファイル共有、およびプリンターなどのオンプレミスのリソースへのアクセスも許可するには、 [AZURE AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)を使用して、オンプレミスの active Directory を Azure active directory と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e0e-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> 

<span data-ttu-id="19e0e-106">詳細については、「 [Azure Active Directory でのデバイス管理の概要](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19e0e-106">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span>
<span data-ttu-id="19e0e-107">手順の概要についても、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="19e0e-107">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="19e0e-108">Azure AD Connect を実行する</span><span class="sxs-lookup"><span data-stu-id="19e0e-108">Run Azure AD Connect</span></span>

<span data-ttu-id="19e0e-109">次の手順を実行して、組織の Azure AD に参加しているデバイスがオンプレミスのリソースにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="19e0e-109">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="19e0e-110">ユーザー、グループ、および連絡先をローカルの Active Directory から Azure Active Directory に同期するには、「 [Office 365 のディレクトリ同期のセットアップ](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect を実行します。</span><span class="sxs-lookup"><span data-stu-id="19e0e-110">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="19e0e-111">ディレクトリ同期が完了したら、組織の Windows 10 デバイスが Azure AD に参加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19e0e-111">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="19e0e-112">この手順は、各 Windows 10 デバイスで個別に実行します。</span><span class="sxs-lookup"><span data-stu-id="19e0e-112">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="19e0e-113">詳細については、「 [Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19e0e-113">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="19e0e-114">Windows 10 デバイスが Azure AD に参加している場合、各ユーザーはデバイスを再起動し、Microsoft 365 Business 資格情報を使用してログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e0e-114">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="19e0e-115">これで、すべてのデバイスがオンプレミスのリソースにもアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="19e0e-115">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="19e0e-116">Azure AD に参加しているデバイスのオンプレミスのリソースにアクセスするために、追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="19e0e-116">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="19e0e-117">これは、Windows 10 で使用可能な組み込みの機能です。</span><span class="sxs-lookup"><span data-stu-id="19e0e-117">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="19e0e-118">前述の Azure AD に参加しているデバイス構成に組織が展開する準備ができていない場合は、[ハイブリッド AZURE ad の参加](manage-windows-devices.md)しているデバイス構成を設定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="19e0e-118">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="19e0e-119">Windows デバイスを Azure AD に参加させる際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="19e0e-119">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="19e0e-120">以前にドメインに参加していた、またはワークグループ内にある Windows デバイスに Azure AD が参加している場合は、次の制限事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e0e-120">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="19e0e-121">デバイス Azure AD が参加すると、既存のプロファイルを参照せずに新しいユーザーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="19e0e-121">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="19e0e-122">この問題を解決するには、プロファイルを手動で移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e0e-122">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="19e0e-123">ユーザープロファイルには、お気に入り、ローカルファイル、ブラウザーの設定、スタートメニューの設定などの情報が含まれています。最善の方法は、既存のファイルと設定を新しいプロファイルにマップするためのサードパーティ製ツールを見つけることです。</span><span class="sxs-lookup"><span data-stu-id="19e0e-123">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="19e0e-124">デバイスがグループポリシーオブジェクト (GPO) を使用している場合、一部の Gpo には Intune での同等の[構成サービスプロバイダー](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) が含まれていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="19e0e-124">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="19e0e-125">[Mmat ツール](https://www.microsoft.com/download/details.aspx?id=45520)を実行して、既存の gpo の同等の csp を検索します。</span><span class="sxs-lookup"><span data-stu-id="19e0e-125">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="19e0e-126">ユーザーは、Active Directory 認証に依存するアプリケーションに対して認証を行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="19e0e-126">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="19e0e-127">これに対処するには、レガシアプリを使用して評価し、可能であればモダン認証を使用するアプリに更新することを検討します。</span><span class="sxs-lookup"><span data-stu-id="19e0e-127">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="19e0e-128">Active Directory プリンターの検出は機能しません。</span><span class="sxs-lookup"><span data-stu-id="19e0e-128">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="19e0e-129">この問題を解決するには、すべてのユーザーの直接プリンターパスを提供するか、[ハイブリッドクラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を利用します。</span><span class="sxs-lookup"><span data-stu-id="19e0e-129">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
