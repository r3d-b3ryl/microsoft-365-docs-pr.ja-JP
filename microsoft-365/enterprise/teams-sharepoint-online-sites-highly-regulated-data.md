---
title: Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: セキュリティで保護された SharePoint Online チームサイトまたは Microsoft Teams のチームを作成し、最も重要で機密性の高いデジタル資産を保存します。
ms.openlocfilehash: fa1a57d898e4822d0c96d6eb807d0a14a815e29a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869006"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="99e09-103">Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには</span><span class="sxs-lookup"><span data-stu-id="99e09-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="99e09-104">**概要:** セキュリティで保護された SharePoint Online チームサイトまたは Microsoft Teams のチームを作成し、最も重要で機密性の高いデジタル資産を保存します。</span><span class="sxs-lookup"><span data-stu-id="99e09-104">**Summary:** Create a secure SharePoint Online team site or a Microsoft Teams team to store your most valuable and sensitive digital assets.</span></span>

<span data-ttu-id="99e09-p101">Microsoft 365 Enterprise には、高度な規制データを作成、保存、保護する一連のクラウドベースのサービスが用意されており、次のようなデータを扱います。</span><span class="sxs-lookup"><span data-stu-id="99e09-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="99e09-107">地域の規制を遵守しているデータ。</span><span class="sxs-lookup"><span data-stu-id="99e09-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="99e09-108">企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータ。</span><span class="sxs-lookup"><span data-stu-id="99e09-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="99e09-109">上記のビジネス ニーズを満たす Microsoft 365 Enterprise のクラウドベースのソリューションでは、以下のことが求められます。</span><span class="sxs-lookup"><span data-stu-id="99e09-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="99e09-110">SharePoint Online チーム サイトまたは Microsoft Teams のチームの **[ファイル]** タブの、デジタル資産 (ドキュメント、スライド セット、スプレッドシートなど) を保存する。</span><span class="sxs-lookup"><span data-stu-id="99e09-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="99e09-111">サイトまたはチームをロックダウンし、以下を防止する。</span><span class="sxs-lookup"><span data-stu-id="99e09-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="99e09-112">グループ メンバーシップ (これには、だれが SharePoint Online チームサイトにどんなアクセス許可のレベルでアクセスできるか、また、だれがそのアクセス許可を管理できるかが含まれる) によるユーザー アカウントの特定のセットを除くすべてのものへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="99e09-112">Access to all except a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="99e09-113">サイトのメンバーから他のユーザーへのアクセス許可の付与。</span><span class="sxs-lookup"><span data-stu-id="99e09-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="99e09-114">サイトのメンバーでないユーザーからサイトへのアクセス要求。</span><span class="sxs-lookup"><span data-stu-id="99e09-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="99e09-115">サイトのデジタル資産を分類する既定の方法として、SharePoint Online サイトまたはチームの Office 365 ラベルを構成する。</span><span class="sxs-lookup"><span data-stu-id="99e09-115">Configure an Office 365 label for your SharePoint Online sites or teams as a default way to classify digital assets on the site.</span></span>
- <span data-ttu-id="99e09-116">ユーザーがファイルを組織外に送信できないようにする。</span><span class="sxs-lookup"><span data-stu-id="99e09-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="99e09-117">サイトやチームの最も機密性の高いデジタル資産を暗号化する。</span><span class="sxs-lookup"><span data-stu-id="99e09-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="99e09-118">最も機密性の高いデジタル資産がサイト外で共有されて、その資産を開く場合にも、アクセス許可のあるユーザー アカウントの有効な資格情報が必要となるように、デジタル資産にアクセス許可を追加する。</span><span class="sxs-lookup"><span data-stu-id="99e09-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="99e09-119">次の表は、上記ソリューションの要件と Microsoft 365 Enterprise の機能を関連付けたものです。</span><span class="sxs-lookup"><span data-stu-id="99e09-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="99e09-120">**要件**</span><span class="sxs-lookup"><span data-stu-id="99e09-120">**Requirement**</span></span> | <span data-ttu-id="99e09-121">**Microsoft 365 Enterprise の機能**</span><span class="sxs-lookup"><span data-stu-id="99e09-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="99e09-122">デジタル資産の保存</span><span class="sxs-lookup"><span data-stu-id="99e09-122">Store digital assets</span></span> | <span data-ttu-id="99e09-123">SharePoint Online チーム サイトと Office 365 のチーム</span><span class="sxs-lookup"><span data-stu-id="99e09-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="99e09-124">サイトのロックダウン</span><span class="sxs-lookup"><span data-stu-id="99e09-124">Lock down the site</span></span> | <span data-ttu-id="99e09-125">Azure AD グループおよび SharePoint Online チーム サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="99e09-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="99e09-126">サイトのデジタル資産のラベル付け</span><span class="sxs-lookup"><span data-stu-id="99e09-126">Label the digital assets of the site</span></span> | <span data-ttu-id="99e09-127">Office 365 ラベル</span><span class="sxs-lookup"><span data-stu-id="99e09-127">Office 365 Labels</span></span> |
| <span data-ttu-id="99e09-128">ユーザーがファイルを組織外に送信できないようにする</span><span class="sxs-lookup"><span data-stu-id="99e09-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="99e09-129">Office 365 のデータ損失防止 (DLP) ポリシー</span><span class="sxs-lookup"><span data-stu-id="99e09-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="99e09-130">サイトのすべてのデジタル資産の暗号化</span><span class="sxs-lookup"><span data-stu-id="99e09-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="99e09-131">Enterprise Mobility + Security (EMS) での Azure Information Protection サブラベル</span><span class="sxs-lookup"><span data-stu-id="99e09-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="99e09-132">サイトのデジタル資産へのアクセス許可の追加</span><span class="sxs-lookup"><span data-stu-id="99e09-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="99e09-133">手順 3: EMS での Azure Information Protection サブラベル</span><span class="sxs-lookup"><span data-stu-id="99e09-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="99e09-134">このソリューションでは、以下のものを既に展開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e09-134">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="99e09-135">[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="99e09-135">Your [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span> 
- <span data-ttu-id="99e09-136">[SharePoint Online](sharepoint-online-onedrive-workload.md) (SharePoint Online チームサイトで高度な規制データを扱う場合)。</span><span class="sxs-lookup"><span data-stu-id="99e09-136">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="99e09-137">[Microsoft Teams](teams-workload.md) (Microsoft Teams のチームで高度な規制データを扱う場合)。</span><span class="sxs-lookup"><span data-stu-id="99e09-137">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="99e09-138">以下のフェーズでは、高度な規制データを扱う SharePoint Online サイトおよびチームの設計、構成、導入方法について、順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="99e09-138">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="99e09-139">架空の多国籍組織を表す Contoso 社が研究チーム向けに SharePoint Online サイトを設計した方法について確認するには、こちらの[構成例](contoso-sharepoint-online-site-for-highly-confidential-assets.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99e09-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

>[!Note]
><span data-ttu-id="99e09-p102">チームで高度な規制データを扱う場合、高度な規制データを扱う SharePoint Online チーム サイトを最初に作成する必要があります。次に、SharePoint Online チーム サイトの Office 365 グループを使用する新しいチームを作成します。詳細については、フェーズ 2 の手順 4 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e09-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>
>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="99e09-143">ID とデバイスのアクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="99e09-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="99e09-144">チームまたは SharePoint Online サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint Online アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e09-144">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="99e09-145">フェーズ 1: 設計</span><span class="sxs-lookup"><span data-stu-id="99e09-145">Phase 1: Design</span></span>

<span data-ttu-id="99e09-p103">高度な規制データを扱う SharePoint Online サイトまたはチームを作成するには、まずその目的を特定する必要があります。たとえば、製造組織の研究開発部門では、既存製品の現在の設計仕様を保存し新製品の共同作業を行う場所として、SharePoint Online サイトが必要になります。この場合、研究開発部門のメンバーと、選択されている役員のみがサイトにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="99e09-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="99e09-149">目的に基づいて、以下のような必須の構成項目を決定します。</span><span class="sxs-lookup"><span data-stu-id="99e09-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="99e09-150">SharePoint Online のアクセス許可一式と SharePoint グループのセット</span><span class="sxs-lookup"><span data-stu-id="99e09-150">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="99e09-151">アクセス グループ一式 (SharePoint グループに追加する Azure AD セキュリティ グループとそのグループのメンバー)</span><span class="sxs-lookup"><span data-stu-id="99e09-151">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="99e09-152">サイトに割り当てる Office 365 ラベルと、そのラベル用の一連の DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="99e09-152">The Office 365 label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="99e09-153">サイトに保存されている機密性の高いデジタル資産にユーザーが適用する Azure Information Protection サブラベルの設定</span><span class="sxs-lookup"><span data-stu-id="99e09-153">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="99e09-154">上記の項目を決定したら、それらの設定に基づき、フェーズ 2 でサイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="99e09-154">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="99e09-155">手順 1: 独立した SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="99e09-155">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="99e09-p104">ロックダウンされたバージョンの SharePoint Online チーム サイトは、独立したサイトとして知られています。プライベート チーム サイトの既定の設定とは異なり、独立サイトは、以下ことを防ぐように構成されます。</span><span class="sxs-lookup"><span data-stu-id="99e09-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="99e09-158">指定したグループのメンバーではないユーザーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="99e09-158">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="99e09-159">アクセスの要求。</span><span class="sxs-lookup"><span data-stu-id="99e09-159">The requesting of access.</span></span>
- <span data-ttu-id="99e09-160">指定されたグループの現在のメンバーによる、無許可のアクセス付与。</span><span class="sxs-lookup"><span data-stu-id="99e09-160">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="99e09-161">アクセス グループのメンバーによるサイトの管理。</span><span class="sxs-lookup"><span data-stu-id="99e09-161">Administration of the site by access group members.</span></span>

<span data-ttu-id="99e09-162">高度に規制された資産が含まれる SharePoint Online チーム サイトのセキュリティは、サイトの SharePoint 管理者のみが変更できます。</span><span class="sxs-lookup"><span data-stu-id="99e09-162">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="99e09-163">一連のアクセス許可レベル、SharePoint グループ、アクセス グループ、グループ メンバーのセットの決定方法の詳細については、「[独立した SharePoint Online チーム サイトの設計](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e09-163">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-labels-and-dlp-policies"></a><span data-ttu-id="99e09-164">手順 2: Office 365 ラベルと DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="99e09-164">Step 2: Office 365 labels and DLP policies</span></span>

<span data-ttu-id="99e09-165">SharePoint Online チーム サイトに適用されると、Office 365 ラベルは、サイトに保存されているすべてのデジタル資産を分類する既定のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="99e09-165">When applied to a SharePoint Online team site, Office 365 labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="99e09-166">SharePoint Online サイトで高度な規制データを扱う場合は、どの Office 365 ラベルを使用するかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e09-166">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 label to use.</span></span>

<span data-ttu-id="99e09-167">Office 365 ラベルの設計の考慮事項については、「[Office 365 の分類とラベル](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files#office-365-classification-and-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e09-167">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files#office-365-classification-and-labels).</span></span>

<span data-ttu-id="99e09-p105">機密性の高い情報を保護し、偶発的または意図的な開示を防止するためには、DLP ポリシーを使用します。詳細については、DLP ポリシーの[概要](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e09-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="99e09-170">SharePoint Online サイトで高度な規制データを扱うには、デジタル資産を外部のユーザーと共有しようとするユーザーをブロックするために、サイトに割り当てられた Office 365 ラベルの DLP ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e09-170">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="99e09-171">手順 3: Azure Information Protection サブラベル</span><span class="sxs-lookup"><span data-stu-id="99e09-171">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="99e09-p106">最も機密性の高いデジタル資産を暗号化し、一連のアクセス許可を付与する場合、ユーザーは、Azure Information Protection クライアントを使用して Azure Information Protection のラベルを適用する必要があります。SharePoint Online サイトの Azure Information Protection のラベルを使用して高度な規制データを扱うには、スコープ指定されたポリシーに Azure Information Protection サブラベルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e09-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="99e09-p107">サブラベルは既存のラベルに含まれます。たとえば、機密性の高いラベルに含まれるラベルとして、研究開発のサブラベルを作成することができます。スコープ指定されたポリシーは、ユーザーのサブセットにのみ適用されるポリシーです。SharePoint Online サイトで高度な規制データを扱う場合、スコープは、サイトのアクセス グループのメンバーである一連のユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="99e09-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="99e09-p108">適用したサブラベルの設定が行われると、サブラベルは資産と共に移動します。サブラベルをダウンロードしてサイト外で共有しても、アクセス許可を持つ認証済みのユーザー アカウントしか、サブラベルを開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="99e09-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

<span data-ttu-id="99e09-180">Azure Information Protection のラベルの設計の考慮事項については、「[Azure Information Protection](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files#azure-information-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e09-180">For the design considerations of Azure Information Protection labels, see [Azure Information Protection](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files#azure-information-protection).</span></span>

### <a name="design-results"></a><span data-ttu-id="99e09-181">設計の結果</span><span class="sxs-lookup"><span data-stu-id="99e09-181">Design results</span></span>

<span data-ttu-id="99e09-182">以下を決定しました。</span><span class="sxs-lookup"><span data-stu-id="99e09-182">You have determined the following:</span></span>

- <span data-ttu-id="99e09-183">SharePoint グループとアクセス許可レベルのセット</span><span class="sxs-lookup"><span data-stu-id="99e09-183">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="99e09-184">アクセス グループと、そのグループのメンバーそれぞれのアクセス許可レベルのセット</span><span class="sxs-lookup"><span data-stu-id="99e09-184">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="99e09-185">適切な Office 365 のラベルと、そのラベルに関連付けられている DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="99e09-185">The appropriate Office 365 label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="99e09-186">暗号化とアクセス許可を含む Azure Information Protection サブラベルの設定</span><span class="sxs-lookup"><span data-stu-id="99e09-186">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="99e09-187">フェーズ 2: 構成</span><span class="sxs-lookup"><span data-stu-id="99e09-187">Phase 2: Configure</span></span>

<span data-ttu-id="99e09-188">このフェーズでは、フェーズ 1 で決定した設定を実装し、高度な規制データを扱う SharePoint Online サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="99e09-188">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="99e09-189">手順 1: 独立した SharePoint Online チーム サイトを作成し構成する</span><span class="sxs-lookup"><span data-stu-id="99e09-189">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="99e09-190">「[独立した SharePoint Online チーム サイトの展開](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)」の手順を参照しながら、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="99e09-190">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="99e09-191">サイトで使用する SharePoint のアクセス許可レベルそれぞれのアクセス グループを作成してデータを設定する。</span><span class="sxs-lookup"><span data-stu-id="99e09-191">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="99e09-192">独立したチーム サイトを作成して構成する。</span><span class="sxs-lookup"><span data-stu-id="99e09-192">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-label-dlp-policy"></a><span data-ttu-id="99e09-193">手順 2: Office 365 ラベルの DLP ポリシー向けにサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="99e09-193">Step 2: Configure the site for an Office 365 label DLP policy</span></span>

<span data-ttu-id="99e09-194">「[Office 365 ラベルと DLP による SharePoint Online ファイルの保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)」の手順を参照しながら、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="99e09-194">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="99e09-195">Office 365 ラベルを特定または作成し、独立した SharePoint Online サイトに適用する。</span><span class="sxs-lookup"><span data-stu-id="99e09-195">Identify or create the Office 365 label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="99e09-196">ユーザーが組織外の SharePoint Online サイトでデジタル資産を共有しようとする場合にユーザーをブロックする DLP ポリシーを作成して構成する。</span><span class="sxs-lookup"><span data-stu-id="99e09-196">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="99e09-197">手順 3: サイト用の Azure Information Protection サブレベルを作成する</span><span class="sxs-lookup"><span data-stu-id="99e09-197">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="99e09-198">「[Azure Information Protection で SharePoint Online ファイルを保護する](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)」の手順を参照しながら、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="99e09-198">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="99e09-199">スコープ指定されたポリシーに Azure Information Protection サブラベルを作成して構成する。</span><span class="sxs-lookup"><span data-stu-id="99e09-199">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="99e09-200">Azure Information Protection クライアントをユーザーのコンピューターに展開する。</span><span class="sxs-lookup"><span data-stu-id="99e09-200">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="99e09-201">手順 4 (省略可能): 高度な規制データを扱うチームを作成する</span><span class="sxs-lookup"><span data-stu-id="99e09-201">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="99e09-p109">高度な規制データを扱うチームが必要な場合は、まず高度な規制データを扱う SharePoint Online サイトを作成します。最初のプライベートの SharePoint Online チーム サイトを作成するときに、Office 365 グループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="99e09-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="99e09-204">高度な規制データを扱う SharePoint Online サイトが完全に構成されたら、次の手順を実行して、高度な規制データを扱うチームに変換します。</span><span class="sxs-lookup"><span data-stu-id="99e09-204">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="99e09-205">Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="99e09-205">Sign in to Office 365.</span></span>
2. <span data-ttu-id="99e09-206">**[Microsoft Office Home]** タブで、**[チーム]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e09-206">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="99e09-207">**[チームに参加またはチームを作成する]** ウィンドウの **[Microsoft Teams]** タブで、**[チームを作成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e09-207">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="99e09-208">**[チームを作成する]** ウィンドウで **[既存の Office 365 グループからチームを作成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e09-208">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="99e09-209">Office 365 グループの一覧から、高度な規制データを扱う SharePoint Online サイトに対応する Office 365 グループの名前を選択し、**[チームを選択する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e09-209">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="99e09-p110">新しいチームの **[ファイル]** タブには、対応する SharePoint Online サイトの**ドキュメント**領域の**一般**フォルダーの内容が一覧表示されます。チームの SharePoint Online サイトの残りのリソースを表示するには、省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e09-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="99e09-212">構成の結果</span><span class="sxs-lookup"><span data-stu-id="99e09-212">Configuration results</span></span>

<span data-ttu-id="99e09-213">以下を構成しました。</span><span class="sxs-lookup"><span data-stu-id="99e09-213">You have configured the following:</span></span>

- <span data-ttu-id="99e09-214">SharePoint Online の独立したサイト</span><span class="sxs-lookup"><span data-stu-id="99e09-214">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="99e09-215">独立した SharePoint Online サイトに割り当てられている Office 365 ラベル</span><span class="sxs-lookup"><span data-stu-id="99e09-215">An Office 365 label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="99e09-216">Office 365 ラベルの DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="99e09-216">A DLP policy for the Office 365 label</span></span>
- <span data-ttu-id="99e09-217">スコープ指定されたポリシーの Azure Information Protection サブラベル。スコープ指定されたポリシーは、ユーザーがサイトに保存されている最も機密性の高いデジタル資産に適用できるポリシーで、保存先のサイトでは資産の暗号化とアクセス許可の付与が行われる</span><span class="sxs-lookup"><span data-stu-id="99e09-217">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="99e09-218">SharePoint Online サイトをベースとした高度な規制データを扱うチーム (必要な場合に作成)</span><span class="sxs-lookup"><span data-stu-id="99e09-218">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="99e09-219">フェーズ 3: ユーザーによる採用を主導する</span><span class="sxs-lookup"><span data-stu-id="99e09-219">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="99e09-p111">SharePoint Online サイトまたはチームが高度な規制データを保護できるのは、機密性の高いデジタル資産の保存とその資産へのアクセスのために、それがコンスタントに使用される場合だけです。このフェーズは、ユーザーのやり方の変更に依存する最も難しいフェーズとなります。</span><span class="sxs-lookup"><span data-stu-id="99e09-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="99e09-222">たとえば、役員が機密ファイルを USB ドライブや個人のクラウドベースのストレージ ソリューションに保存していた場合、その役員は、高度な規制データを扱う SharePoint Online サイトまたはチームだけに機密ファイルを保存するようになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e09-222">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="99e09-223">手順 1: ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="99e09-223">Step 1: Train your users</span></span>

<span data-ttu-id="99e09-224">構成が完了したら、サイトのアクセス グループのメンバーである一連のユーザーを以下の面でトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="99e09-224">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="99e09-225">貴重な資産を保護するために新しいサイトやチームを使用することの重要性と、高度な規制データのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。</span><span class="sxs-lookup"><span data-stu-id="99e09-225">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="99e09-226">サイトとその資産へのアクセス方法。</span><span class="sxs-lookup"><span data-stu-id="99e09-226">How to access the site and its assets.</span></span>
- <span data-ttu-id="99e09-227">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="99e09-227">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="99e09-228">DLP ポリシーを使用して、外部からのファイルの共有をできないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="99e09-228">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="99e09-229">Azure Information Protection クライアントを使用して、構成したサブラベルで最も機密性の高いデジタル資産にラベル付けをする方法。</span><span class="sxs-lookup"><span data-stu-id="99e09-229">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="99e09-230">サイトやチームから資産がリークした場合でも、Azure Information Protection サブラベルによって資産を保護する方法。</span><span class="sxs-lookup"><span data-stu-id="99e09-230">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="99e09-231">このトレーニングには、ユーザーが上記の操作とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e09-231">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="99e09-232">手順 2: 使用状況とファイルの定期的なレビューの実施</span><span class="sxs-lookup"><span data-stu-id="99e09-232">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="99e09-233">トレーニングの数週間後、SharePoint Online サイトまたはチームの SharePoint 管理者は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="99e09-233">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="99e09-234">サイトまたはチームの使用状況を分析し、それが期待された使用法と一致しているかを比較する。</span><span class="sxs-lookup"><span data-stu-id="99e09-234">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="99e09-235">機密性の高いファイルに Azure Information Protection サブラベルが正しくラベル付けされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="99e09-235">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="99e09-236">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="99e09-236">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="99e09-237">ユーザーによる採用の結果</span><span class="sxs-lookup"><span data-stu-id="99e09-237">User adoption results</span></span>

<span data-ttu-id="99e09-238">機密性の高いデジタル資産は、高度な規制データを扱う SharePoint Online サイトまたはチームだけに保存され、最も機密性の高い資産には Azure Information Protection サブラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="99e09-238">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="99e09-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="99e09-239">See also</span></span>

[<span data-ttu-id="99e09-240">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="99e09-240">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="99e09-241">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="99e09-241">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="99e09-242">開発/テスト環境の SharePoint Online サイトをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="99e09-242">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
