---
title: 'ステップ 5: Office 365 データ損失防止を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 の Office 365 データ損失防止を理解して展開する。
ms.openlocfilehash: dbe88885812e51b0daefa89dae123af5907c60a8
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047250"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="60a3f-103">ステップ 5: Office 365 データ損失防止を構成する</span><span class="sxs-lookup"><span data-stu-id="60a3f-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="60a3f-104">*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="60a3f-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="60a3f-105">Office 365 セキュリティ/コンプライアンス センターのデータ損失防止 (DLP) ポリシーを使用することにより、Microsoft 365 全体で機密情報の識別、監視、自動保護を行えます。</span><span class="sxs-lookup"><span data-stu-id="60a3f-105">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="60a3f-106">DLP ポリシーを使用すると、以下を行えます:</span><span class="sxs-lookup"><span data-stu-id="60a3f-106">With DLP policies, you can:</span></span>

- <span data-ttu-id="60a3f-107">Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams などの複数の保管場所での機密情報の識別。 </span><span class="sxs-lookup"><span data-stu-id="60a3f-107">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="60a3f-108">ドキュメントへのアクセスのブロックや機密情報を含むメールのブロックによる、意図しない機密情報の共有の防止。</span><span class="sxs-lookup"><span data-stu-id="60a3f-108">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="60a3f-109">デスクトップ バージョンの Excel、PowerPoint、Word 内の機密情報の監視と保護。</span><span class="sxs-lookup"><span data-stu-id="60a3f-109">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="60a3f-110">ワークフローを中断することなく遵守を維持する方法をユーザーが理解できるようにするための、メール通知とポリシー ヒントによるサポート。</span><span class="sxs-lookup"><span data-stu-id="60a3f-110">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="60a3f-111">組織の DLP ポリシーと一致するコンテンツを示す DLP レポートの表示。</span><span class="sxs-lookup"><span data-stu-id="60a3f-111">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="60a3f-112">DLP ポリシーは、以下を指定します:</span><span class="sxs-lookup"><span data-stu-id="60a3f-112">A DLP policy specifies:</span></span>

- <span data-ttu-id="60a3f-113">**場所:** Exchange Online、SharePoint Online、OneDrive for Business のサイトの他、Microsoft Teams のチャットおよびチャネルなどの保管場所。</span><span class="sxs-lookup"><span data-stu-id="60a3f-113">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="60a3f-114">**日時:** コンテンツが一致する必要のある特定のポリシー ルール内の条件。　</span><span class="sxs-lookup"><span data-stu-id="60a3f-114">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="60a3f-115">**方法:** 一致する条件に対して自動的に実行される、一致するポリシー ルールが指定するアクション。</span><span class="sxs-lookup"><span data-stu-id="60a3f-115">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="60a3f-116">つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60a3f-116">In other words:</span></span>

- <span data-ttu-id="60a3f-117">条件に一致する保管場所にあるドキュメントに対して (場所)、そのコンテンツがルールの条件に一致する場合 (日時)、そのルールが指定するアクションが自動的に実行されます (方法)。</span><span class="sxs-lookup"><span data-stu-id="60a3f-117">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="60a3f-118">必要な DLP ポリシー セットの決定に際しては、データ損失からの保護を必要とするドキュメントおよびそれらに含まれるデータの種類を分析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60a3f-118">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="60a3f-119">たとえば、米国の金融機関の場合が、社会保障番号を含むドキュメントが組織外部と共有されたり組織外部の場所にメールで送信されたりすることを防止する DLP を作成するとします。</span><span class="sxs-lookup"><span data-stu-id="60a3f-119">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="60a3f-120">次に、DLP の正常な動作を確認して誤検知を最小化するために、テスト用の保管場所を使用してポリシーの構成とテストを行います。</span><span class="sxs-lookup"><span data-stu-id="60a3f-120">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="60a3f-121">最後に、新しいポリシーおよびそれらが指定する動作を従業員に告知し、保管場所の適用範囲を広げます。このようにしてポリシーを組織で展開します。</span><span class="sxs-lookup"><span data-stu-id="60a3f-121">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="60a3f-122">詳細については、「[DLP ポリシーの推奨事項について](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60a3f-122">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="60a3f-123">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="60a3f-123">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="60a3f-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="60a3f-124">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="60a3f-125">電子メールの暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="60a3f-125">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


