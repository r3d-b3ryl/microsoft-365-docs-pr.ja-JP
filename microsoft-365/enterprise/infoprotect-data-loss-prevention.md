---
title: 'ステップ 5: Office 365 データ損失防止を構成する'
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 896670e9ae83324a1220d64f49a8ea48aee85169
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067224"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="887be-103">ステップ 5: Office 365 データ損失防止を構成する</span><span class="sxs-lookup"><span data-stu-id="887be-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="887be-104">*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="887be-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="887be-106">Office 365 セキュリティ/コンプライアンス センターのデータ損失防止 (DLP) ポリシーを使用することにより、Microsoft 365 全体で機密情報の識別、監視、自動保護を行えます。</span><span class="sxs-lookup"><span data-stu-id="887be-106">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="887be-107">DLP ポリシーを使用すると、以下を行えます:</span><span class="sxs-lookup"><span data-stu-id="887be-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="887be-108">Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams などの複数の保管場所での機密情報の識別。 </span><span class="sxs-lookup"><span data-stu-id="887be-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="887be-109">ドキュメントへのアクセスのブロックや機密情報を含むメールのブロックによる、意図しない機密情報の共有の防止。</span><span class="sxs-lookup"><span data-stu-id="887be-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="887be-110">デスクトップ バージョンの Excel、PowerPoint、Word 内の機密情報の監視と保護。</span><span class="sxs-lookup"><span data-stu-id="887be-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="887be-111">ワークフローを中断することなく遵守を維持する方法をユーザーが理解できるようにするための、メール通知とポリシー ヒントによるサポート。</span><span class="sxs-lookup"><span data-stu-id="887be-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="887be-112">組織の DLP ポリシーと一致するコンテンツを示す DLP レポートの表示。</span><span class="sxs-lookup"><span data-stu-id="887be-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="887be-113">DLP ポリシーは、以下を指定します:</span><span class="sxs-lookup"><span data-stu-id="887be-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="887be-114">**場所:** Exchange Online、SharePoint Online、OneDrive for Business のサイトの他、Microsoft Teams のチャットおよびチャネルなどの保管場所。</span><span class="sxs-lookup"><span data-stu-id="887be-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="887be-115">**日時:** コンテンツが一致する必要のある特定のポリシー ルール内の条件。　</span><span class="sxs-lookup"><span data-stu-id="887be-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="887be-116">**方法:** 一致する条件に対して自動的に実行される、一致するポリシー ルールが指定するアクション。</span><span class="sxs-lookup"><span data-stu-id="887be-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="887be-117">つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="887be-117">In other words:</span></span>

- <span data-ttu-id="887be-118">条件に一致する保管場所にあるドキュメントに対して (場所)、そのコンテンツがルールの条件に一致する場合 (日時)、そのルールが指定するアクションが自動的に実行されます (方法)。</span><span class="sxs-lookup"><span data-stu-id="887be-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="887be-119">必要な DLP ポリシー セットの決定に際しては、データ損失からの保護を必要とするドキュメントおよびそれらに含まれるデータの種類を分析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="887be-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="887be-120">たとえば、米国の金融機関の場合が、社会保障番号を含むドキュメントが組織外部と共有されたり組織外部の場所にメールで送信されたりすることを防止する DLP を作成するとします。</span><span class="sxs-lookup"><span data-stu-id="887be-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="887be-121">次に、DLP の正常な動作を確認して誤検知を最小化するために、テスト用の保管場所を使用してポリシーの構成とテストを行います。</span><span class="sxs-lookup"><span data-stu-id="887be-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="887be-122">最後に、新しいポリシーおよびそれらが指定する動作を従業員に告知し、保管場所の適用範囲を広げます。このようにしてポリシーを組織で展開します。</span><span class="sxs-lookup"><span data-stu-id="887be-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="887be-123">詳細については、「[DLP ポリシーの推奨事項について](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="887be-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="887be-124">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="887be-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="887be-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="887be-125">Next step</span></span>

|||
|:-------|:-----|
|![手順 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="887be-127">電子メールの暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="887be-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


