---
title: ユーザーのディレクトリ同期をMicrosoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: ユーザーとオンプレミスの Active Directory の間Microsoft 365同期を設定する方法について学習します。
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924906"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="e1604-103">ユーザーのディレクトリ同期をMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="e1604-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="e1604-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="e1604-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e1604-105">Microsoft 365は、Azure Active Directory (Azure AD) テナントを使用して、クラウドベースのリソースにアクセスするための認証とアクセス許可の ID を格納および管理します。</span><span class="sxs-lookup"><span data-stu-id="e1604-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="e1604-106">オンプレミスの Active Directory ドメイン サービス (AD DS) ドメインまたはフォレストがある場合は、AD DS ユーザー アカウント、グループ、および連絡先を Microsoft 365 サブスクリプションの Azure AD テナントと同期できます。</span><span class="sxs-lookup"><span data-stu-id="e1604-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="e1604-107">これは、ユーザーのハイブリッド id Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e1604-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="e1604-108">そのコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e1604-108">Here are its components.</span></span>

![ディレクトリ同期のコンポーネント (Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="e1604-110">Azure AD Connectオンプレミス サーバー上で実行され、DS と Azure ADテナントをADします。</span><span class="sxs-lookup"><span data-stu-id="e1604-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="e1604-111">ディレクトリ同期と共に、次の認証オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1604-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="e1604-112">パスワード ハッシュ同期 (PHS)</span><span class="sxs-lookup"><span data-stu-id="e1604-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="e1604-113">Azure AD認証自体を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1604-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="e1604-114">パススルー認証 (PTA)</span><span class="sxs-lookup"><span data-stu-id="e1604-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="e1604-115">Azure AD DS AD認証を実行しています。</span><span class="sxs-lookup"><span data-stu-id="e1604-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="e1604-116">フェデレーション認証</span><span class="sxs-lookup"><span data-stu-id="e1604-116">Federated authentication</span></span>

  <span data-ttu-id="e1604-117">Azure ADは、認証を要求するクライアント コンピューターを別の ID プロバイダーに参照します。</span><span class="sxs-lookup"><span data-stu-id="e1604-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="e1604-118">詳細 [については、「ハイブリッド ID」](plan-for-directory-synchronization.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1604-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="e1604-119">1. Azure の前提条件を確認AD Connect</span><span class="sxs-lookup"><span data-stu-id="e1604-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="e1604-120">サブスクリプションで無料の Azure ADサブスクリプションをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="e1604-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="e1604-121">ディレクトリ同期を設定すると、Azure AD Connectオンプレミス サーバーの 1 つにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1604-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="e1604-122">このMicrosoft 365、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1604-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="e1604-123">オンプレミス ドメインを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1604-123">Verify your on-premises domain.</span></span> <span data-ttu-id="e1604-124">Azure AD Connectウィザードでは、この手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="e1604-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="e1604-125">テナントおよび DS の管理者アカウントのユーザー名とパスワードMicrosoft 365取得ADします。</span><span class="sxs-lookup"><span data-stu-id="e1604-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="e1604-126">Azure AD Connectをインストールするオンプレミス サーバーの場合は、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1604-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="e1604-127">**サーバー OS**</span><span class="sxs-lookup"><span data-stu-id="e1604-127">**Server OS**</span></span>|<span data-ttu-id="e1604-128">**その他のソフトウェア**</span><span class="sxs-lookup"><span data-stu-id="e1604-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1604-129">Windows Server 2012R2 以降</span><span class="sxs-lookup"><span data-stu-id="e1604-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="e1604-130">- PowerShell は既定でインストールされ、アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e1604-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="e1604-131">- Net 4.5.1 以降のリリースは、更新プログラムを通じてWindowsされます。</span><span class="sxs-lookup"><span data-stu-id="e1604-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="e1604-132">コントロール パネルにサーバーに最新の更新Windowsインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1604-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="e1604-133">WindowsService Pack 1 (SP1)\*\* またはサーバー 2008 R2 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e1604-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="e1604-134">- PowerShell の最新バージョンは、Windows Management Framework 4.0 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1604-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="e1604-135">Microsoft ダウンロード センターで [検索します](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="e1604-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="e1604-136">- .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センターで利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="e1604-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="e1604-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="e1604-137">Windows Server 2008</span></span> | <span data-ttu-id="e1604-138">- サポートされている最新バージョンの PowerShell は、Microsoft ダウンロード センター Windows Management Framework 3.0 から[利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="e1604-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="e1604-139">- .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センターで利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="e1604-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="e1604-140">Azure [Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)のハードウェア、ソフトウェア、アカウント、およびアクセス許可の要件、SSL 証明書の要件、およびオブジェクトの制限の詳細については、「前提条件」を参照AD Connect。</span><span class="sxs-lookup"><span data-stu-id="e1604-140">See [Prerequisites for Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="e1604-141">また、Azure AD Connect[バージョン](/azure/active-directory/hybrid/reference-connect-version-history)のリリース履歴を確認して、各リリースに含まれているものと修正された情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e1604-141">You can also review the Azure AD Connect [version release history](/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="e1604-142">2. Azure AD Connectをインストールし、ディレクトリ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="e1604-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="e1604-143">開始する前に、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1604-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="e1604-144">グローバル管理者のユーザー名Microsoft 365パスワード</span><span class="sxs-lookup"><span data-stu-id="e1604-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="e1604-145">DS ドメイン管理者のユーザー ADパスワード</span><span class="sxs-lookup"><span data-stu-id="e1604-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="e1604-146">どの認証方法 (PHS、PTA、フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="e1604-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="e1604-147">シームレス シングル サインオン [(SSO) で Azure ADを使用するかどうか](/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="e1604-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="e1604-148">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1604-148">Follow these steps:</span></span>

1. <span data-ttu-id="e1604-149">管理センターのMicrosoft 365 [サインインし](https://admin.microsoft.com)、 https://admin.microsoft.com) 左側のナビゲーションで [**ユーザー** \> **のアクティブユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1604-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="e1604-150">[アクティブ ユーザー **] ページで** 、[その他 ( **3** つのドット) ディレクトリ同期] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e1604-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="e1604-151">[準備 **Azure Active Directoryページで**、[ダウンロード センターに移動] を選択して **、[Azure AD Connectツール**] リンクを取得して開始します。</span><span class="sxs-lookup"><span data-stu-id="e1604-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="e1604-152">Azure AD Connect[および Azure AD Connect 正常性インストール のロードマップの手順に従います](/azure/active-directory/hybrid/how-to-connect-install-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="e1604-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="e1604-153">3. ドメインの設定を完了する</span><span class="sxs-lookup"><span data-stu-id="e1604-153">3. Finish setting up domains</span></span>

<span data-ttu-id="e1604-154">DNS レコードを管理してドメインのセットアップをMicrosoft 365するときに、「ドメインの DNS レコード[を](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)作成する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e1604-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1604-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1604-155">Next step</span></span>

[<span data-ttu-id="e1604-156">ユーザー アカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e1604-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)