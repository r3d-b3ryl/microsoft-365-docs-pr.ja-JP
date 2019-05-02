---
title: 'ステップ 5: Office 365 データ損失防止を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 で Office 365 データ損失防止を理解して展開します。
ms.openlocfilehash: d0a8beae3797e59eb1eb130afb9fd123be57d909
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308353"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="58dc7-103">ステップ 5: Office 365 データ損失防止を構成する</span><span class="sxs-lookup"><span data-stu-id="58dc7-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="58dc7-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="58dc7-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="58dc7-105">Office 365 セキュリティ & コンプライアンス センターのデータ損失防止 (DLP) ポリシーにより、Microsoft 365 全体の機密情報の識別、監視、自動保護ができます。</span><span class="sxs-lookup"><span data-stu-id="58dc7-105">Protection of personal information in Office 365 includes using data loss prevention capabilities. With data loss prevention (DLP) policies in the Office 365 Security & Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span> <span data-ttu-id="58dc7-106">DLP ポリシーを用いて次が行えます:</span><span class="sxs-lookup"><span data-stu-id="58dc7-106">With DLP, you can:</span></span>

- <span data-ttu-id="58dc7-107">Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams などの複数の保管場所のまたがる機密情報を識別します。 </span><span class="sxs-lookup"><span data-stu-id="58dc7-107">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>
- <span data-ttu-id="58dc7-108">ドキュメントへのアクセスをブロックしたり、機密情報を含むメールをブロックしたりすることで、意図しない機密情報の共有を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="58dc7-108">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="58dc7-109">デスクトップ バージョンの Excel、PowerPoint、Word 内の機密情報を監視し、保護します。</span><span class="sxs-lookup"><span data-stu-id="58dc7-109">Monitor and protect sensitive information in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016.</span></span>
- <span data-ttu-id="58dc7-110">メール通知とポリシー ヒントを用いて、ワークフローを中断することなく準拠した状態を保つ方法をユーザーが理解するのを助けます。</span><span class="sxs-lookup"><span data-stu-id="58dc7-110">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="58dc7-111">組織の DLP ポリシーと一致するコンテンツを示す DLP レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="58dc7-111">View DLP reports showing content that matches your organization’s DLP policies.</span></span>

<span data-ttu-id="58dc7-112">DLP ポリシーでは次を指定します:</span><span class="sxs-lookup"><span data-stu-id="58dc7-112">A DLP policy specifies:</span></span>

- <span data-ttu-id="58dc7-113">**場所:** Microsoft Teams のチャットおよびチャネルと、Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teamsなどの保管場所。</span><span class="sxs-lookup"><span data-stu-id="58dc7-113">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="58dc7-114">**日時:** 特定のポリシー ルールの範囲内でコンテンツが一致する必要のある条件。　</span><span class="sxs-lookup"><span data-stu-id="58dc7-114">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="58dc7-115">**方法:** ポリシー ルールに一致している範囲内での一致条件に対応する自動的なアクション。</span><span class="sxs-lookup"><span data-stu-id="58dc7-115">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="58dc7-116">つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="58dc7-116">In other words:</span></span>

- <span data-ttu-id="58dc7-117">上記の保管場所内 (場所) のドキュメントの場合、ルール (日時) の条件がコンテンツと一致していれば、ルールで指定されたアクション (方法) を自動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="58dc7-117">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="58dc7-118">必要な DLP ポリシー セットを決定するには、データ損失からの保護を必要とする範囲内のドキュメントとデータの種類を解析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58dc7-118">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="58dc7-119">たとえば、米国の金融機関の場合は、社会保障番号と共にドキュメントが組織の外で共有されたり、組織の外の保管場所にメールで送信されたりするのを防ぐ DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="58dc7-119">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="58dc7-120">次に、正しい DLP の動作を保証して誤検知を最小化するところの保管場所のテストと共にポリシーの設定とテストを行います。</span><span class="sxs-lookup"><span data-stu-id="58dc7-120">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="58dc7-121">最後に、従業員の新しいポリシーと従業員として望ましい行動の通知と、保管場所の適用範囲の拡張を行うことにより、組織へとそのポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="58dc7-121">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="58dc7-122">詳細については、[DLP のポリシー勧告を見る](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58dc7-122">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="58dc7-123">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="58dc7-123">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="58dc7-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="58dc7-124">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="58dc7-125">Office 365 の特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="58dc7-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


