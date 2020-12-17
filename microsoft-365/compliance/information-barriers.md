---
title: Microsoft 365 の情報障壁について
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
description: 情報バリアを使用して、組織内で Microsoft Teams を使用して通信コンプライアンスを確保します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73a76e67fdb96f89dbd11daf4b2ef12f6590f92a
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701006"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a><span data-ttu-id="41623-103">Microsoft 365 の情報障壁について</span><span class="sxs-lookup"><span data-stu-id="41623-103">Learn about information barriers in Microsoft 365</span></span>

<span data-ttu-id="41623-104">Microsoft クラウド サービスには、強力な通信機能とコラボレーション機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="41623-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="41623-105">ただし、組織内で関心の競合が発生しないように、2 つのグループ間の通信とコラボレーションを制限するとします。</span><span class="sxs-lookup"><span data-stu-id="41623-105">But suppose that you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="41623-106">または、内部情報を保護するために、組織内の特定のユーザー間の通信とコラボレーションを制限したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="41623-106">Or, perhaps you want to restrict communication and collaboration between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="41623-107">Microsoft 365 を使用すると、グループや組織間でのコミュニケーションとコラボレーションが可能になります。そのため、必要に応じて、特定のユーザー グループ間の通信とコラボレーションを制限する方法はありますか?</span><span class="sxs-lookup"><span data-stu-id="41623-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communication and collaboration  among specific groups of users when necessary?</span></span> <span data-ttu-id="41623-108">情報バリアを使用すると、可能です。</span><span class="sxs-lookup"><span data-stu-id="41623-108">With information barriers, you can!</span></span> 

<span data-ttu-id="41623-109">Microsoft Teams、SharePoint Online、OneDrive for Business で情報バリアがサポートされました。</span><span class="sxs-lookup"><span data-stu-id="41623-109">Information barriers is now supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="41623-110">サブスクリプションに [情報](#required-licenses-and-permissions) バリアが含まれる場合、コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザー グループ間の通信を許可または防止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="41623-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="41623-111">情報バリア ポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="41623-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="41623-112">一日の業者グループのユーザーは、マーケティング チームと通信したり、ファイルを共有したりしなけず</span><span class="sxs-lookup"><span data-stu-id="41623-112">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="41623-113">会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしなき</span><span class="sxs-lookup"><span data-stu-id="41623-113">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="41623-114">営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーに電話したり、オンラインでチャットしたりしなき</span><span class="sxs-lookup"><span data-stu-id="41623-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="41623-115">研究チームは、製品開発チームに電話するか、オンラインでチャットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41623-115">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41623-116">情報バリア \* は **_ 2** つの方法の制限のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="41623-116">Information barriers \***only supports** _ two way restrictions.</span></span> <span data-ttu-id="41623-117">マーケティングなどの一方的な制限は、日の業者と通信できますが、日の業者はマーケティング _\* と通信できません\*\* は _サポート_ されていません。</span><span class="sxs-lookup"><span data-stu-id="41623-117">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing _\*_is not supported_\*\*.</span></span>

<span data-ttu-id="41623-118">これらのすべてのシナリオ例 (およびそれ以上) では、Microsoft Teams での通信を防止または許可する情報バリア ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="41623-118">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="41623-119">このようなポリシーを使用すると、ユーザーが通話やチャットを行わないか、Microsoft Teams の特定のグループとのみ通信できます。</span><span class="sxs-lookup"><span data-stu-id="41623-119">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="41623-120">情報バリア ポリシーが有効な場合、それらのポリシーの対象となるユーザーが Microsoft Teams の他のユーザーと通信しようとするたびに、(情報バリア ポリシーで定義されている) 通信を防止 (または許可) するためのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="41623-120">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="41623-121">情報障壁のあるユーザー エクスペリエンスの詳細については [、Microsoft Teams の情報バリアを参照してください](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="41623-121">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41623-122">現在、情報バリアは電子メール通信には適用されません。</span><span class="sxs-lookup"><span data-stu-id="41623-122">Currently, information barriers do not apply to email communications.</span></span> <span data-ttu-id="41623-123">さらに、情報バリアはコンプライアンスの境界 [から独立しています](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="41623-123">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="41623-124">情報バリア ポリシーを定義して適用する前に、組織に Exchange アドレス帳ポリシーが [有効で](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) なされていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="41623-124">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="41623-125">(情報バリアはアドレス帳ポリシーに基づく)</span><span class="sxs-lookup"><span data-stu-id="41623-125">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="41623-126">情報バリアの発生</span><span class="sxs-lookup"><span data-stu-id="41623-126">What happens with information barriers</span></span>

<span data-ttu-id="41623-127">情報バリア ポリシーが適用されている場合、他の特定のユーザーとファイルの通信や共有を行う必要のあるユーザーは、それらのユーザーの検索、選択、チャット、または呼び出しを行うことはありません。</span><span class="sxs-lookup"><span data-stu-id="41623-127">When information barrier policies are in place, people who should not communicate or share files with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="41623-128">情報バリアを使用して、承認されていない通信を防止するためのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="41623-128">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="41623-129">最初は、情報バリアは Microsoft Teams のチャットとチャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="41623-129">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="41623-130">Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。</span><span class="sxs-lookup"><span data-stu-id="41623-130">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>

- <span data-ttu-id="41623-131">ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="41623-131">Searching for a user</span></span>
- <span data-ttu-id="41623-132">チームにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="41623-132">Adding a member to a team</span></span>
- <span data-ttu-id="41623-133">他のユーザーとのチャット セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="41623-133">Starting a chat session with someone</span></span>
- <span data-ttu-id="41623-134">グループ チャットを開始する</span><span class="sxs-lookup"><span data-stu-id="41623-134">Starting a group chat</span></span>
- <span data-ttu-id="41623-135">ユーザーを会議に招待する</span><span class="sxs-lookup"><span data-stu-id="41623-135">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="41623-136">画面を共有する</span><span class="sxs-lookup"><span data-stu-id="41623-136">Sharing a screen</span></span>
- <span data-ttu-id="41623-137">電話をかける</span><span class="sxs-lookup"><span data-stu-id="41623-137">Placing a call</span></span>
- <span data-ttu-id="41623-138">別のユーザーとファイルを共有する</span><span class="sxs-lookup"><span data-stu-id="41623-138">Sharing a file with another user</span></span>
- <span data-ttu-id="41623-139">共有リンクを使用してファイルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="41623-139">Access to file through sharing link</span></span> 

<span data-ttu-id="41623-140">関係するユーザーが、活動を防止する情報バリア ポリシーに含まれている場合、続行できません。</span><span class="sxs-lookup"><span data-stu-id="41623-140">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="41623-141">さらに、情報バリア ポリシーに含まれているすべてのユーザーは、Microsoft Teams で他のユーザーと通信できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="41623-141">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="41623-142">情報バリア ポリシーの影響を受けるユーザーが同じチームまたはグループ チャットの一部である場合、それらのユーザーがチャット セッションから削除され、グループとのそれ以上の通信が許可されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="41623-142">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="41623-143">情報障壁のあるユーザー エクスペリエンスの詳細については [、Microsoft Teams の情報バリアを参照してください](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="41623-143">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="41623-144">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="41623-144">Required licenses and permissions</span></span>

<span data-ttu-id="41623-145">情報バリアは現在展開中であり、次のようなサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="41623-145">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="41623-146">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="41623-146">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="41623-147">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="41623-147">Office 365 E5/A5</span></span>
- <span data-ttu-id="41623-148">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="41623-148">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="41623-149">Microsoft 365 コンプライアンス E5/A5</span><span class="sxs-lookup"><span data-stu-id="41623-149">Microsoft 365 Compliance E5/A5</span></span>
- <span data-ttu-id="41623-150">Microsoft 365 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="41623-150">Microsoft 365 Insider Risk Management</span></span>

<span data-ttu-id="41623-151">詳細については、セキュリティとコンプライアンス [に関する Microsoft 365 ライセンス ガイダンス&覧ください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="41623-151">For more details, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

<span data-ttu-id="41623-152">情報 [バリア ポリシーを定義または編集するには、](information-barriers-policies.md)次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="41623-152">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="41623-153">Microsoft 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="41623-153">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="41623-154">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="41623-154">Office 365 global administrator</span></span>
- <span data-ttu-id="41623-155">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="41623-155">Compliance administrator</span></span>
- <span data-ttu-id="41623-156">IB コンプライアンス管理 (これは新しい役割です)</span><span class="sxs-lookup"><span data-stu-id="41623-156">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="41623-157">(役割とアクセス許可の詳細については、「Office [365 セキュリティ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)/コンプライアンス センター&アクセス許可」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="41623-157">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="41623-158">情報バリア ポリシーを定義、検証、または編集するには、PowerShell コマンドレットに精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="41623-158">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="41623-159">方法に関する記事では PowerShell コマンドレットのいくつかの例[](information-barriers-policies.md)を示しますが、組織のパラメーターなど、追加の詳細を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="41623-159">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="41623-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="41623-160">Next steps</span></span>

- [<span data-ttu-id="41623-161">Microsoft Teams の情報障壁の詳細</span><span class="sxs-lookup"><span data-stu-id="41623-161">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="41623-162">情報バリア ポリシーに使用できる属性を確認する</span><span class="sxs-lookup"><span data-stu-id="41623-162">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="41623-163">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="41623-163">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="41623-164">情報バリア ポリシーの編集 (または削除)</span><span class="sxs-lookup"><span data-stu-id="41623-164">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)
- [<span data-ttu-id="41623-165">SharePoint Online の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="41623-165">Learn more about Information barriers in SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/information-barriers)
- [<span data-ttu-id="41623-166">OneDrive for Business の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="41623-166">Learn more about Information barriers in OneDrive for Business</span></span>](https://docs.microsoft.com/onedrive/information-barriers)