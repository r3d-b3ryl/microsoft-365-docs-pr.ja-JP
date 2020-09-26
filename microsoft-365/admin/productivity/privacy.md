---
title: Microsoft プロダクティビティスコア-プライバシー
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: 生産性スコアによるプライバシーの保護
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287300"
---
# <a name="privacy-controls-for-productivity-score"></a><span data-ttu-id="35532-103">生産性スコアのプライバシー制御</span><span class="sxs-lookup"><span data-stu-id="35532-103">Privacy controls for Productivity Score</span></span>

<span data-ttu-id="35532-104">生産性スコアは、ユーザーが Microsoft 365 を使用する方法と、それらをサポートするテクノロジエクスペリエンスについて、組織がどのように作業を遂行するかを分析するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35532-104">Productivity Score helps organizations transform how work gets done with insights about how people use Microsoft 365 and the technology experiences that support them.</span></span> <span data-ttu-id="35532-105">このスコアは、組織&#39;のパフォーマンスを従業員やテクノロジの体験手段に照らして反映し、自分のスコアを自分のような組織と比較します。</span><span class="sxs-lookup"><span data-stu-id="35532-105">The score reflects your organization&#39;s performance against employee and technology experience measures and compares your score with organizations like yours.</span></span> <span data-ttu-id="35532-106">詳細については、「 [生産性スコアの概要](productivity-score.md) 」のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35532-106">For more details, check out the [Productivity Score overview](productivity-score.md) topic.</span></span>

<span data-ttu-id="35532-107">お客様のプライバシーは我々にとって重要であり、Microsoft のプライバシーに関する声明は [こちらで](https://privacy.microsoft.com/privacystatement)ご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="35532-107">Your privacy is important to us and you can view Microsoft's privacy statement [here](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="35532-108">生産性スコアでは、組織内のユーザーがどのように機能するかについて、重要な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="35532-108">In Productivity Score, there is vital information that we provide on how people in your organizations work.</span></span> <span data-ttu-id="35532-109">そのため、弊社では、お客様の信頼を侵害せずに、意味のある方法で情報が操作可能であることを確認するための制御を提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="35532-109">Thus, we also aim to provide you controls to make sure the information is actionable in a meaningful way while not compromising the trust you place in us.</span></span>

<span data-ttu-id="35532-110">データをより安全に処理できるように、次のコントロールを用意しています。</span><span class="sxs-lookup"><span data-stu-id="35532-110">We provide the following controls to allow for safer handling of data:</span></span>

- <span data-ttu-id="35532-111">生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割。</span><span class="sxs-lookup"><span data-stu-id="35532-111">Flexible admin roles to control who can see the information in Productivity Score.</span></span>
- <span data-ttu-id="35532-112">ユーザーレベルの指標の匿名化。</span><span class="sxs-lookup"><span data-stu-id="35532-112">Anonymization of user level metrics.</span></span>
- <span data-ttu-id="35532-113">従業員の利便性をオプトアウトする機能。</span><span class="sxs-lookup"><span data-stu-id="35532-113">Capability to opt out of Employee experience.</span></span>

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a><span data-ttu-id="35532-114">生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割</span><span class="sxs-lookup"><span data-stu-id="35532-114">Flexible admin roles to control who can see the information in Productivity Score</span></span>

<span data-ttu-id="35532-115">テナントレベルの洞察、ユーザーごとのレベルの詳細を含む、管理者の役割を使用して生産性のスコアを表示するには、役割が次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="35532-115">To view the entire Productivity Score experience with an admin role, including tenant level insights and per-user level details, your role should be one of the following:</span></span>

- <span data-ttu-id="35532-116">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="35532-116">Global admin</span></span>
- <span data-ttu-id="35532-117">Exchange の管理者</span><span class="sxs-lookup"><span data-stu-id="35532-117">Exchange admins</span></span>
- <span data-ttu-id="35532-118">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="35532-118">SharePoint admin</span></span>
- <span data-ttu-id="35532-119">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="35532-119">Skype for Business admin</span></span>
- <span data-ttu-id="35532-120">Teams 管理者</span><span class="sxs-lookup"><span data-stu-id="35532-120">Teams admin</span></span>
- <span data-ttu-id="35532-121">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="35532-121">Global Reader</span></span>
- <span data-ttu-id="35532-122">レポート閲覧者</span><span class="sxs-lookup"><span data-stu-id="35532-122">Reports Reader</span></span>

<span data-ttu-id="35532-123">変更の管理と導入を担当するが、IT 管理者ではないユーザーに対して、テナントレベルの洞察やユーザーごとの詳細情報を含む完全な機能へのアクセスを許可している場合は、それらのユーザーにレポートリーダーの役割を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="35532-123">To invite people who are responsible for change management and adoption but are not IT administrators into the experience, while giving them access to the complete experience including tenant level insights and per-user level details, you can give them Report Reader role.</span></span>

<span data-ttu-id="35532-124">従業員の経験の範囲内で、カテゴリ詳細ページごとにユーザーごとのレベルのアクティビティの詳細をグリッド形式で提供します。</span><span class="sxs-lookup"><span data-stu-id="35532-124">Within Employee experience, we provide per-user level activity details in grid format for each category detail page.</span></span> <span data-ttu-id="35532-125">このレベルの詳細は、生産性スコアの可能性があるすべての訪問者には適していないため、Azure AD-利用状況の概要レポート閲覧者ロールにカスタムロールを作成しました。これにより、組織内のより広範な訪問者に対して、集約された指標のみにアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="35532-125">As this level of detail is not suitable for all potential visitors of Productivity Score, we have created a custom role within Azure AD – Usage Summary Reports Reader role – to enable access to a wider set of visitors within your org to only the aggregate metrics and no per-level details within the experience.</span></span>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="生産性レポートの [通信] ページ":::

## <a name="anonymization-of-user-level-metrics"></a><span data-ttu-id="35532-127">ユーザーレベルの指標の匿名化</span><span class="sxs-lookup"><span data-stu-id="35532-127">Anonymization of user level metrics</span></span>

<span data-ttu-id="35532-128">すべてのレポートで匿名で収集されるデータを作成するには、全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="35532-128">To make the data that is collected for all reports anonymous, you must be a global administrator.</span></span> <span data-ttu-id="35532-129">これにより、生産性スコアや Microsoft 365 の使用状況を含む、すべてのレポートのユーザー、グループ、サイト名など、識別可能な情報が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="35532-129">This will hide identifiable information such as user, group, and site names in all reports – including Productivity Score and Microsoft 365 Usage.</span></span>

1. <span data-ttu-id="35532-130">管理センターで、[設定] [ **Settings**   >   **組織設定**] に移動し、[**サービス**] タブの [**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="35532-130">In the admin center, go to the  **Settings**  >  **Org Settings** , and under  **Services**  tab, choose  **Reports**.</span></span>
2. <span data-ttu-id="35532-131">[  **レポート** ] を選択し、[  **生産性スコアと利用状況レポート] にユーザー、グループ、およびサイト名の匿名識別子を表示**するように選択します。</span><span class="sxs-lookup"><span data-stu-id="35532-131">Select  **Reports** , and then choose to  **Display anonymous identifiers for user, group and site names in Productivity Score and Usage Reports**.</span></span> <span data-ttu-id="35532-132">この設定は、利用状況レポートだけでなく、テンプレートアプリにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="35532-132">This setting gets applied both to the usage reports as well as to the template app.</span></span>
3. <span data-ttu-id="35532-133">[  **Save changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="35532-133">Select  **Save changes**.</span></span>

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="ユーザー情報をレポート用に匿名にします。":::

## <a name="capability-to-opt-out-of-employee-experience"></a><span data-ttu-id="35532-135">従業員の experience をオプトアウトする機能</span><span class="sxs-lookup"><span data-stu-id="35532-135">Capability to opt out of Employee experience</span></span>

<span data-ttu-id="35532-136">また、全般的な可用性で、生産性スコアの従業員経験領域をオプトアウトする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="35532-136">We will also provide the capability to opt out of the Employee experience area of Productivity Score at general availability.</span></span> <span data-ttu-id="35532-137">この設定をオンにすると、組織内のすべてのユーザーがこれらの指標を表示したり、カテゴリの通信、会議、チームワーク、コンテンツコラボレーション、モビリティを含むすべての計算から組織を削除したりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="35532-137">Turning this setting on will prevent anyone from your organization being able to view these metrics and remove your organization from any calculations involving categories of Communication, Meetings, Teamwork, Content collaboration and Mobility.</span></span>

1. <span data-ttu-id="35532-138">管理センターで、[設定] [ **Settings**   >   **組織設定**] に移動し、[**サービス**] タブの [**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="35532-138">In the admin center, go to the  **Settings**  >  **Org Settings** , and under  **Services**  tab, choose  **Reports**.</span></span>
2. <span data-ttu-id="35532-139">[  **レポート** ] を選択し、[  **組織&#39;のデータを生産性スコアの従業員が**利用できるようにする] というボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="35532-139">Select  **Reports** , and then un-check the box that says  **Share your org&#39;s data with Productivity Score Employee Experience insights**.</span></span> <span data-ttu-id="35532-140">Intune 構成マネージャーでエンドポイント分析のデータ共有設定を変更する方法について理解するには、[ **詳細情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35532-140">To understand how to modify data-sharing settings for Endpoint Analytics in the Intune configuration manager, click on **Learn More**.</span></span>
3. <span data-ttu-id="35532-141">[  **Save changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="35532-141">Select  **Save changes**.</span></span>

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="[組織の設定] ページ従業員の利便性から選択できます。":::