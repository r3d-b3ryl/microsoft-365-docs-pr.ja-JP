---
title: アクセスは、オンプレミス マイクロソフト 365 ビジネスで Azure AD に参加しているデバイスからのリソース
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 基幹業務アプリケーション、ファイル共有、および Azure Active Directory からプリンターに Windows の 10 のデバイスが参加しているように、オンプレミスのリソースへのアクセスを取得する方法について説明します。
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869026"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="b52fa-103">アクセスは、オンプレミス マイクロソフト 365 ビジネスで Azure AD に参加しているデバイスからのリソース</span><span class="sxs-lookup"><span data-stu-id="b52fa-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="b52fa-p101">Azure Active directory が参加しているすべての Windows 10 デバイスは Office 365 アプリケーションなどのすべてのクラウド ベースのリソースへのアクセスがあり、Microsoft 365 のビジネスを保護します。基幹業務 (LOB) アプリケーション、ファイル共有、およびプリンターのように、オンプレミスのリソースへのアクセス許可、 [Azure AD 接続](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)を使用して、Azure Active Directory で、オンプレミスの Active Directory を同期する必要があります。[Azure Active Directory 内のデバイスの管理の概要](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52fa-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="b52fa-107">実行 Azure AD 接続します。</span><span class="sxs-lookup"><span data-stu-id="b52fa-107">Run Azure AD Connect</span></span>

<span data-ttu-id="b52fa-108">設置型のリソースにアクセスするための組織の Azure AD が参加しているデバイスを有効にするのには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="b52fa-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="b52fa-109">Azure Active Directory に、ユーザー、グループ、およびローカルの Active Directory から連絡先を同期するには、ディレクトリの同期ウィザードを実行して、Azure AD 接続は、 [Office 365 のディレクトリ同期の設定](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="b52fa-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="b52fa-p102">ディレクトリ同期処理が完了したら、組織の Windows 10 のデバイスは、Azure AD が参加していることを確認します。この手順は、Windows 10 デバイスごとに個別に行われます。詳細については[Microsoft 365 ビジネス ユーザー向けの Windows デバイスの設定](set-up-windows-devices.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52fa-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="b52fa-p103">10 の Windows のデバイスには、Azure AD が参加しているが、各ユーザーは、デバイスと Microsoft 365 ビジネス資格情報でログイン再起動します。すべてのデバイスも、オンプレミスのリソースへのアクセスがされます。</span><span class="sxs-lookup"><span data-stu-id="b52fa-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="b52fa-p104">追加の手順は、オンプレミス AD の Azure のリソースには、デバイスが参加しているへのアクセスを取得するために必要ではありません。これは、10 の Windows で使用できる組み込みの機能です。</span><span class="sxs-lookup"><span data-stu-id="b52fa-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="b52fa-117">組織が構成では、Azure AD 参加しているデバイス上で説明した展開する準備がない場合は、[ハイブリッド Azure AD 参加済みのデバイス構成](manage-windows-devices.md)の設定を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b52fa-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="b52fa-118">Azure AD に、Windows のデバイスを結合する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="b52fa-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="b52fa-119">Azure AD のドメインに参加されていた Windows デバイスを結合する場合、またはワークグループでは、次の制限事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52fa-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="b52fa-p105">デバイス Azure AD に参加する場合は、既存のプロファイルを参照することがなく新しいユーザーを作成します。これを修正するには、プロファイルを手動で移行する必要があります。ユーザー プロファイルには、[お気に入り]、[ローカル ファイル、ブラウザーの設定、[スタート] メニューの設定などのような情報が含まれています。最善のアプローチは、既存のファイルおよび設定を新しいプロファイルにマップするサードパーティ製のツールを見つけること</span><span class="sxs-lookup"><span data-stu-id="b52fa-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="b52fa-p106">デバイスがグループ ポリシー オブジェクト (GPO) を使用しているいくつかの Gpo 必要はありません同等[構成サービス プロバイダー](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) Intune で。[MMAT ツール](https://www.microsoft.com/download/details.aspx?id=45520)に匹敵する Csp を既存の Gpo の検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="b52fa-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="b52fa-p107">ユーザーは Active Directory 認証に依存するアプリケーションを認証することができません。対処するためこのレガシ アプリケーションを使用して評価し、可能な場合は最新の認証を使用するアプリケーションへの更新を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b52fa-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="b52fa-p108">アクティブ ディレクトリのプリンターの検出は行われません。これを修正するには、直接プリンターのパスを提供するすべてのユーザーまたは[ハイブリッド クラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を活用します。</span><span class="sxs-lookup"><span data-stu-id="b52fa-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

