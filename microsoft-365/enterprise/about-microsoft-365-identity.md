---
title: Microsoft 365 ID モデルと Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: クラウド専用またはハイブリッド ID モデルを使用AD Microsoft 365 で Azure ユーザー ID サービスを管理する方法について説明します。
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905706"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="13ba5-103">Microsoft 365 ID モデルと Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13ba5-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="13ba5-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="13ba5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="13ba5-105">Microsoft 365 は、Microsoft 365 サブスクリプションに含まれるクラウドベースのユーザー ID および認証サービスである Azure Active Directory (Azure AD) を使用して、Microsoft 365 の ID と認証を管理します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="13ba5-106">組織の Microsoft 365 ユーザー アクセスとアクセス許可を管理するには、ID インフラストラクチャを正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ba5-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="13ba5-107">開始する前に、Microsoft 365 の ID モデルと認証の概要についてこのビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13ba5-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="13ba5-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="13ba5-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="13ba5-109">最初の計画の選択は、Microsoft 365 ID モデルです。</span><span class="sxs-lookup"><span data-stu-id="13ba5-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="13ba5-110">Microsoft 365 ID モデル</span><span class="sxs-lookup"><span data-stu-id="13ba5-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="13ba5-111">ユーザー アカウントを計画するには、まず Microsoft 365 の 2 つの ID モデルを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ba5-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="13ba5-112">組織の ID はクラウドでのみ維持するか、オンプレミスの Active Directory ドメイン サービス (AD DS) ID を維持し、ユーザーが Microsoft 365 クラウド サービスにアクセスするときに認証に使用できます。</span><span class="sxs-lookup"><span data-stu-id="13ba5-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="13ba5-113">ID の 2 種類と、最適なフィット感と利点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="13ba5-114">属性</span><span class="sxs-lookup"><span data-stu-id="13ba5-114">Attribute</span></span> | <span data-ttu-id="13ba5-115">クラウド専用 ID</span><span class="sxs-lookup"><span data-stu-id="13ba5-115">Cloud-only identity</span></span> | <span data-ttu-id="13ba5-116">ハイブリッド ID</span><span class="sxs-lookup"><span data-stu-id="13ba5-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="13ba5-117">**定義**</span><span class="sxs-lookup"><span data-stu-id="13ba5-117">**Definition**</span></span> | <span data-ttu-id="13ba5-118">ユーザー アカウントは、Microsoft 365 サブスクリプションの Azure ADテナントにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="13ba5-119">ユーザー アカウントは DS AD存在し、コピーは Microsoft 365 サブスクリプションの Azure ADテナントにも存在します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="13ba5-120">Azure ADのユーザー アカウントには、既にハッシュされた DS ユーザー アカウント のパスワードADが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="13ba5-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="13ba5-121">**Microsoft 365 がユーザー資格情報を認証する方法**</span><span class="sxs-lookup"><span data-stu-id="13ba5-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="13ba5-122">Microsoft 365 ADの Azure クライアント テナントは、クラウド ID アカウントを使用して認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="13ba5-123">Microsoft 365 サブスクリプションの Azure ADテナントは、認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="13ba5-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="13ba5-124">**最適シナリオ**</span><span class="sxs-lookup"><span data-stu-id="13ba5-124">**Best for**</span></span> | <span data-ttu-id="13ba5-125">DS を使用するオンプレミスの組織または必要AD組織。</span><span class="sxs-lookup"><span data-stu-id="13ba5-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="13ba5-126">DS または別AD ID プロバイダーを使用している組織。</span><span class="sxs-lookup"><span data-stu-id="13ba5-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="13ba5-127">**最大のメリット**</span><span class="sxs-lookup"><span data-stu-id="13ba5-127">**Greatest benefit**</span></span> | <span data-ttu-id="13ba5-128">使いやすい。</span><span class="sxs-lookup"><span data-stu-id="13ba5-128">Simple to use.</span></span> <span data-ttu-id="13ba5-129">追加のディレクトリ ツールやサーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="13ba5-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="13ba5-130">ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="13ba5-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="13ba5-131">クラウド専用 ID</span><span class="sxs-lookup"><span data-stu-id="13ba5-131">Cloud-only identity</span></span>

<span data-ttu-id="13ba5-132">クラウド専用 ID は、Azure アカウントにのみ存在するユーザー アカウントを使用AD。</span><span class="sxs-lookup"><span data-stu-id="13ba5-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="13ba5-133">クラウド専用 ID は、通常、オンプレミス のサーバーを持たない、またはローカル ID を管理するために AD DS を使用しない小規模な組織で使用されます。</span><span class="sxs-lookup"><span data-stu-id="13ba5-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="13ba5-134">クラウド専用 ID の基本的なコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-134">Here are the basic components of cloud-only identity.</span></span>
 
![クラウド専用 ID の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="13ba5-136">オンプレミスユーザーとリモート (オンライン) ユーザーの両方が、Azure ADとパスワードを使用して Microsoft 365 クラウド サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="13ba5-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="13ba5-137">Azure AD、保存されているユーザー アカウントとパスワードに基づいてユーザー資格情報を認証します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="13ba5-138">管理</span><span class="sxs-lookup"><span data-stu-id="13ba5-138">Administration</span></span>
<span data-ttu-id="13ba5-139">ユーザー アカウントは Azure AD にのみ格納されるので[、Microsoft 365](../admin/add-users/index.yml)管理センターや管理センターなどのツールを使用してクラウド[ID をWindows PowerShell。](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="13ba5-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](../admin/add-users/index.yml) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="13ba5-140">ハイブリッド ID</span><span class="sxs-lookup"><span data-stu-id="13ba5-140">Hybrid identity</span></span>

<span data-ttu-id="13ba5-141">ハイブリッド ID は、オンプレミスの DS からAD、Microsoft 365 サブスクリプションの Azure AD テナントにコピーを持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="13ba5-142">ただし、ほとんどの変更は 1 つの方法でのみフローします。</span><span class="sxs-lookup"><span data-stu-id="13ba5-142">However, most changes only flow one way.</span></span> <span data-ttu-id="13ba5-143">DS ユーザー アカウントに対して行AD変更は、Azure ユーザー アカウントのコピーと同期AD。</span><span class="sxs-lookup"><span data-stu-id="13ba5-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="13ba5-144">ただし、Azure AD のクラウドベースのアカウント (新しいユーザー アカウントなど) に加えた変更は、AD DS と同期されません。</span><span class="sxs-lookup"><span data-stu-id="13ba5-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="13ba5-145">Azure AD Connect は、継続的なアカウント同期を提供します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="13ba5-146">オンプレミス サーバー上で実行し、DS の変更をADし、それらの変更を Azure サーバーに転送AD。</span><span class="sxs-lookup"><span data-stu-id="13ba5-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="13ba5-147">Azure AD Connect では、同期するアカウントと、パスワード ハッシュ同期 (PHS) と呼ばれるハッシュバージョンのユーザー パスワードを同期するかどうかをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="13ba5-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="13ba5-148">ハイブリッド ID を実装する場合、オンプレミスの AD DS がアカウント情報の権限を持つソースになります。</span><span class="sxs-lookup"><span data-stu-id="13ba5-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="13ba5-149">つまり、主にオンプレミスで管理タスクを実行し、Azure サーバーに同期AD。</span><span class="sxs-lookup"><span data-stu-id="13ba5-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="13ba5-150">ハイブリッド ID のコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-150">Here are the components of hybrid identity.</span></span>

![ハイブリッド ID のコンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="13ba5-152">Azure ADテナントには、DS アカウントのADがあります。</span><span class="sxs-lookup"><span data-stu-id="13ba5-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="13ba5-153">この構成では、Microsoft 365 クラウド サービスにアクセスするオンプレミスユーザーとリモート ユーザーの両方が Azure AD に対して認証されます。</span><span class="sxs-lookup"><span data-stu-id="13ba5-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="13ba5-154">ハイブリッド ID のユーザー アカウントを同期するには、常に Azure AD接続を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ba5-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="13ba5-155">ライセンスの割り当てとグループAD、アクセス許可の構成、およびユーザー アカウントに関連するその他の管理タスクを実行するには、Azure AD で同期されたユーザー アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="13ba5-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="13ba5-156">管理</span><span class="sxs-lookup"><span data-stu-id="13ba5-156">Administration</span></span>

<span data-ttu-id="13ba5-157">元のユーザー アカウントと権限のあるユーザー アカウントはオンプレミスの AD DS に格納されますので、AD DS を管理するのと同じツールを使用して id を管理します。</span><span class="sxs-lookup"><span data-stu-id="13ba5-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="13ba5-158">Microsoft 365 管理センターまたは PowerShell for Microsoft 365 を使用して、Azure AD で同期されたユーザー アカウントを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="13ba5-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="13ba5-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="13ba5-159">Next step</span></span>

<span data-ttu-id="13ba5-160">クラウド専用 ID モデルが必要な場合は、「クラウド専用 [ID」を参照してください](cloud-only-identities.md)。</span><span class="sxs-lookup"><span data-stu-id="13ba5-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="13ba5-161">ハイブリッド ID モデルが必要な場合は、「ハイブリッド ID」 [を参照してください](plan-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="13ba5-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="13ba5-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="13ba5-162">See also</span></span>

[<span data-ttu-id="13ba5-163">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="13ba5-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)