---
title: 情報バリアについて
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアを使用して、組織内の Microsoft Teams を使用して通信のコンプライアンスを確保します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41b9eb1378a585a22bbd747edb395b79cfe761ca
ms.sourcegitcommit: c51dd4c659f763ae46c188d3fae90aab8d1d7e88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45084146"
---
# <a name="information-barriers"></a><span data-ttu-id="bef55-103">情報バリア</span><span class="sxs-lookup"><span data-stu-id="bef55-103">Information barriers</span></span>

<span data-ttu-id="bef55-104">Microsoft クラウドサービスには、強力なコミュニケーションとコラボレーションの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bef55-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="bef55-105">しかし、2つのグループ間の通信とコラボレーションを制限して、組織での利益の競合を回避する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="bef55-105">But suppose that you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="bef55-106">または、内部情報を保護するために、組織内の特定のユーザー間のコミュニケーションとコラボレーションを制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bef55-106">Or, perhaps you want to restrict communication and collaboration between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="bef55-107">Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にするため、必要に応じて特定のユーザーグループ間の通信とコラボレーションを制限する方法がありますか。</span><span class="sxs-lookup"><span data-stu-id="bef55-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communication and collaboration  among specific groups of users when necessary?</span></span> <span data-ttu-id="bef55-108">情報バリアを使用して、できることはありません。</span><span class="sxs-lookup"><span data-stu-id="bef55-108">With information barriers, you can!</span></span> 

<span data-ttu-id="bef55-109">Microsoft Teams、SharePoint Online、OneDrive for Business では、情報バリアがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bef55-109">Information barriers is now supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="bef55-110">[サブスクリプション](#required-licenses-and-permissions)に情報の障壁が含まれている場合、コンプライアンス管理者または情報バリア管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="bef55-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="bef55-111">情報バリアポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bef55-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="bef55-112">営業担当営業グループのユーザーは、マーケティングチームとファイルを通信または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="bef55-112">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="bef55-113">機密企業情報を扱う財務担当者は、組織内の特定のグループとファイルを通信または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="bef55-113">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="bef55-114">組織内の特定のグループに属するユーザーとの通信を、取引先機密資料を含む内部チームに対して行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="bef55-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="bef55-115">研究チームは、製品開発チームとの通話またはオンラインチャットのみを行います。</span><span class="sxs-lookup"><span data-stu-id="bef55-115">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bef55-116">情報の障壁は、2つの方法の制限***のみをサポート***します。</span><span class="sxs-lookup"><span data-stu-id="bef55-116">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="bef55-117">マーケティングなどの1つの方法の制限は、マーケティングとは通信できませんが、営業***はサポート***されていません。</span><span class="sxs-lookup"><span data-stu-id="bef55-117">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="bef55-118">これらのすべてのシナリオ例 (およびその他) については、Microsoft Teams での通信を禁止または許可するように情報バリアポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="bef55-118">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="bef55-119">このようなポリシーを使用すると、ユーザーが不要な通話やチャットを行うことができなくなり、Microsoft Teams 内の特定のグループとのみ通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bef55-119">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="bef55-120">情報バリアポリシーが有効になっていると、そのポリシーの対象となっているユーザーが Microsoft Teams 内の他のユーザーと通信しようとするたびに、チェックが行われて、通信 (情報バリアポリシーによって定義されている) を回避 (または許可) します。</span><span class="sxs-lookup"><span data-stu-id="bef55-120">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="bef55-121">情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef55-121">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bef55-122">現時点では、情報バリアは電子メール通信には適用されません。</span><span class="sxs-lookup"><span data-stu-id="bef55-122">Currently, information barriers do not apply to email communications.</span></span> <span data-ttu-id="bef55-123">さらに、情報バリアは、[コンプライアンスの境界](set-up-compliance-boundaries.md)から独立しています。</span><span class="sxs-lookup"><span data-stu-id="bef55-123">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="bef55-124">情報バリアポリシーを定義して適用する前に、組織の[Exchange アドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)が有効になっていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bef55-124">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="bef55-125">(情報障壁はアドレス帳ポリシーに基づいています。)</span><span class="sxs-lookup"><span data-stu-id="bef55-125">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="bef55-126">情報バリアで行われる処理</span><span class="sxs-lookup"><span data-stu-id="bef55-126">What happens with information barriers</span></span>

<span data-ttu-id="bef55-127">情報バリアポリシーが設定されている場合、他の特定のユーザーとのファイルの通信または共有を行わないユーザーは、それらのユーザーを検索、選択、チャット、または呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="bef55-127">When information barrier policies are in place, people who should not communicate or share files with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="bef55-128">情報バリアを使用して、承認されていない通信を防止するためのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="bef55-128">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="bef55-129">最初は、情報の障壁は Microsoft Teams のチャットおよびチャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="bef55-129">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="bef55-130">Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。</span><span class="sxs-lookup"><span data-stu-id="bef55-130">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>

- <span data-ttu-id="bef55-131">ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="bef55-131">Searching for a user</span></span>
- <span data-ttu-id="bef55-132">チームにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="bef55-132">Adding a member to a team</span></span>
- <span data-ttu-id="bef55-133">他のユーザーとのチャット セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="bef55-133">Starting a chat session with someone</span></span>
- <span data-ttu-id="bef55-134">グループ チャットを開始する</span><span class="sxs-lookup"><span data-stu-id="bef55-134">Starting a group chat</span></span>
- <span data-ttu-id="bef55-135">ユーザーを会議に招待する</span><span class="sxs-lookup"><span data-stu-id="bef55-135">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="bef55-136">画面を共有する</span><span class="sxs-lookup"><span data-stu-id="bef55-136">Sharing a screen</span></span>
- <span data-ttu-id="bef55-137">電話をかける</span><span class="sxs-lookup"><span data-stu-id="bef55-137">Placing a call</span></span>
- <span data-ttu-id="bef55-138">別のユーザーとファイルを共有する</span><span class="sxs-lookup"><span data-stu-id="bef55-138">Sharing a file with another user</span></span>
- <span data-ttu-id="bef55-139">共有リンクによるファイルへのアクセス</span><span class="sxs-lookup"><span data-stu-id="bef55-139">Access to file through sharing link</span></span> 

<span data-ttu-id="bef55-140">関係するユーザーが、活動を防止する情報バリア ポリシーに含まれている場合、続行できません。</span><span class="sxs-lookup"><span data-stu-id="bef55-140">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="bef55-141">さらに、情報バリア ポリシーに含まれているすべてのユーザーは、Microsoft Teams で他のユーザーと通信できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bef55-141">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="bef55-142">情報バリア ポリシーの影響を受けるユーザーが同じチームまたはグループ チャットの一部である場合、それらのユーザーがチャット セッションから削除され、グループとのそれ以上の通信が許可されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="bef55-142">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="bef55-143">情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef55-143">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="bef55-144">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="bef55-144">Required licenses and permissions</span></span>

<span data-ttu-id="bef55-145">情報バリアは現在ロールアウトされており、次のようなサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bef55-145">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="bef55-146">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bef55-146">Microsoft 365 E5</span></span>
- <span data-ttu-id="bef55-147">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="bef55-147">Office 365 E5</span></span>
- <span data-ttu-id="bef55-148">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="bef55-148">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="bef55-149">Microsoft 365 コンプライアンス E5</span><span class="sxs-lookup"><span data-stu-id="bef55-149">Microsoft 365 Compliance E5</span></span>

<span data-ttu-id="bef55-150">詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef55-150">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="bef55-151">[情報バリアポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef55-151">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="bef55-152">Microsoft 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="bef55-152">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="bef55-153">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="bef55-153">Office 365 global administrator</span></span>
- <span data-ttu-id="bef55-154">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="bef55-154">Compliance administrator</span></span>
- <span data-ttu-id="bef55-155">IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="bef55-155">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="bef55-156">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](../security/office-365-security/protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef55-156">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="bef55-157">情報バリアポリシーを定義、検証、または編集するには、PowerShell コマンドレットを熟知している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef55-157">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="bef55-158">[「How to](information-barriers-policies.md)」の記事では PowerShell コマンドレットの例をいくつか示していますが、パラメーターなどの追加の詳細については、組織のために知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef55-158">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bef55-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="bef55-159">Next steps</span></span>

- [<span data-ttu-id="bef55-160">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="bef55-160">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="bef55-161">情報バリアポリシーに使用できる属性を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef55-161">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="bef55-162">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="bef55-162">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="bef55-163">情報バリア ポリシーの編集 (または削除)</span><span class="sxs-lookup"><span data-stu-id="bef55-163">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)
- [<span data-ttu-id="bef55-164">SharePoint Online の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="bef55-164">Learn more about Information barriers in SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/information-barriers)
- [<span data-ttu-id="bef55-165">OneDrive for business の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="bef55-165">Learn more about Information barriers in OneDrive for Business</span></span>](https://docs.microsoft.com/onedrive/information-barriers)