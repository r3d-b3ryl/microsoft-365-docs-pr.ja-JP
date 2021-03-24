---
title: Microsoft 365 の情報バリアの詳細
description: 組織内の Microsoft Teams を使用して通信コンプライアンスを確保するには、情報バリアを使用します。
ms.author: robmazz
author: robmazz
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
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051879"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a><span data-ttu-id="47169-103">Microsoft 365 の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="47169-103">Learn about information barriers in Microsoft 365</span></span>

<span data-ttu-id="47169-104">Microsoft クラウド サービスには、強力なコミュニケーションおよびコラボレーション機能が搭載されています。</span><span class="sxs-lookup"><span data-stu-id="47169-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="47169-105">ただし、組織内で利益相反が発生しないように、2 つのグループ間の通信とコラボレーションを制限するとします。</span><span class="sxs-lookup"><span data-stu-id="47169-105">But suppose that you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="47169-106">または、内部情報を保護するために、組織内の特定のユーザー間の通信とコラボレーションを制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="47169-106">Or, perhaps you want to restrict communication and collaboration between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="47169-107">Microsoft 365 では、グループや組織間でのコミュニケーションとコラボレーションが可能なので、必要に応じて特定のグループのユーザー間の通信とコラボレーションを制限する方法はありますか?</span><span class="sxs-lookup"><span data-stu-id="47169-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communication and collaboration  among specific groups of users when necessary?</span></span> <span data-ttu-id="47169-108">情報バリアを使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="47169-108">With information barriers, you can!</span></span>

<span data-ttu-id="47169-109">Microsoft Teams、SharePoint Online、OneDrive for Business では、情報バリアがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="47169-109">Microsoft Teams, SharePoint Online, and OneDrive for Business support information barriers.</span></span> <span data-ttu-id="47169-110">サブスクリプションに [情報](#required-licenses-and-permissions) バリアが含まれると仮定すると、コンプライアンス管理者、または情報バリア管理者は、Microsoft Teams のユーザー グループ間の通信を許可または防止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="47169-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator, or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="47169-111">情報バリア ポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="47169-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="47169-112">当日のトレーダー グループのユーザーは、マーケティング チームとファイルの通信や共有を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="47169-112">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="47169-113">会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしな</span><span class="sxs-lookup"><span data-stu-id="47169-113">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="47169-114">営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーとオンラインで通話したりチャットしたりしな</span><span class="sxs-lookup"><span data-stu-id="47169-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="47169-115">リサーチ チームは、製品開発チームとオンラインでのみ通話またはチャットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47169-115">A research team should only call or chat online with a product development team</span></span>
- <span data-ttu-id="47169-116">デイ トレーダー グループのサイトは、その日のトレーダー グループ外のユーザーが共有したり、アクセスしたりしな</span><span class="sxs-lookup"><span data-stu-id="47169-116">A site for day trader group should not be shared or accessed by anyone outside the day trader group</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47169-117">情報バリア \* は **、** _ 2 つの方法の制限のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="47169-117">Information barriers \***only supports** _ two way restrictions.</span></span> <span data-ttu-id="47169-118">マーケティングなどの 1 つの方法の制限は、デイ トレーダーと通信および共同作業できますが、デイ トレーダーはマーケティング _\* と通信および共同作業することはできません \*\*は _サポート_ されていません。</span><span class="sxs-lookup"><span data-stu-id="47169-118">One way restrictions, such as marketing can communicate and collaborate with day traders, but day traders cannot communicate and collaborate with marketing _\*_is not supported_\*\*.</span></span>

<span data-ttu-id="47169-119">これらすべてのシナリオ例 (およびそれ以上) に関して、Microsoft Teams、SharePoint Online、OneDrive での通信およびコラボレーションを防止または許可するために、情報バリア ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="47169-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications and collaboration in Microsoft Teams, SharePoint Online and OneDrive.</span></span> <span data-ttu-id="47169-120">このようなポリシーを使用すると、ユーザーが通話やチャットを行わないか、Microsoft Teams の特定のグループとのみ通信できます。</span><span class="sxs-lookup"><span data-stu-id="47169-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="47169-121">情報バリア ポリシーが有効な場合、これらのポリシーの対象となるユーザーが Microsoft Teams で他のユーザーとの通信と共同作業を試みるたびに、SharePoint Online または OneDrive のチェックは、(情報バリア ポリシーで定義されている) 通信とコラボレーションを防止 (または許可) するために行われます。</span><span class="sxs-lookup"><span data-stu-id="47169-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate and collaborate with others in Microsoft Teams, SharePoint Online or OneDrive checks are done to prevent (or allow) communication and collaboration (as defined by information barrier policies).</span></span>

<span data-ttu-id="47169-122">情報バリアに関するユーザー エクスペリエンスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47169-122">To learn more about the user experience with information barriers, see:</span></span>

- [<span data-ttu-id="47169-123">Microsoft Teams の情報バリア</span><span class="sxs-lookup"><span data-stu-id="47169-123">Information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="47169-124">SharePoint Online の情報バリア</span><span class="sxs-lookup"><span data-stu-id="47169-124">Information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="47169-125">OneDrive の情報バリア</span><span class="sxs-lookup"><span data-stu-id="47169-125">Information barriers in OneDrive</span></span>](/onedrive/information-barriers)

> [!IMPORTANT]
> <span data-ttu-id="47169-126">現在、情報バリアは電子メール通信には適用されません。</span><span class="sxs-lookup"><span data-stu-id="47169-126">Currently, information barriers do not apply to email communications.</span></span> <span data-ttu-id="47169-127">さらに、情報バリアはコンプライアンスの境界 [とは独立しています](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="47169-127">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p> <span data-ttu-id="47169-128">情報バリア ポリシーを定義して適用する前に、組織に Exchange アドレス帳ポリシーが適用されていないこと [を](/exchange/address-books/address-book-policies/address-book-policies) 確認してください。</span><span class="sxs-lookup"><span data-stu-id="47169-128">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="47169-129">(情報バリアはアドレス帳ポリシーに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="47169-129">(Information barriers are based on address book policies.)</span></span>

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="47169-130">情報バリアで何が起こるか</span><span class="sxs-lookup"><span data-stu-id="47169-130">What happens with information barriers</span></span>

<span data-ttu-id="47169-131">情報バリア ポリシーが適用されている場合、他の特定のユーザーとファイルを通信したり共有したりしなき人は、それらのユーザーを見つけたり、選択したり、チャットしたり、呼び出したりできない。</span><span class="sxs-lookup"><span data-stu-id="47169-131">When information barrier policies are in place, people who should not communicate or share files with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="47169-132">情報バリアにより、不正な通信やコラボレーションを防止するチェックが実施されています。</span><span class="sxs-lookup"><span data-stu-id="47169-132">With information barriers, checks are in place to prevent unauthorized communication and collaboration.</span></span> 

<span data-ttu-id="47169-133">情報バリアは、Microsoft Teams (チャットとチャネル)、SharePoint Online、OneDrive に適用されます。</span><span class="sxs-lookup"><span data-stu-id="47169-133">Information barriers applies to Microsoft Teams (chats and channels), SharePoint Online and OneDrive.</span></span> <span data-ttu-id="47169-134">Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。</span><span class="sxs-lookup"><span data-stu-id="47169-134">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>

- <span data-ttu-id="47169-135">ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="47169-135">Searching for a user</span></span>
- <span data-ttu-id="47169-136">チームにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="47169-136">Adding a member to a team</span></span>
- <span data-ttu-id="47169-137">他のユーザーとのチャット セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="47169-137">Starting a chat session with someone</span></span>
- <span data-ttu-id="47169-138">グループ チャットを開始する</span><span class="sxs-lookup"><span data-stu-id="47169-138">Starting a group chat</span></span>
- <span data-ttu-id="47169-139">ユーザーを会議に招待する</span><span class="sxs-lookup"><span data-stu-id="47169-139">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="47169-140">画面を共有する</span><span class="sxs-lookup"><span data-stu-id="47169-140">Sharing a screen</span></span>
- <span data-ttu-id="47169-141">電話をかける</span><span class="sxs-lookup"><span data-stu-id="47169-141">Placing a call</span></span>
- <span data-ttu-id="47169-142">別のユーザーとファイルを共有する</span><span class="sxs-lookup"><span data-stu-id="47169-142">Sharing a file with another user</span></span>
- <span data-ttu-id="47169-143">共有リンクを使用したファイルへのアクセス</span><span class="sxs-lookup"><span data-stu-id="47169-143">Access to file through sharing link</span></span>

<span data-ttu-id="47169-144">関係するユーザーが、活動を防止する情報バリア ポリシーに含まれている場合、続行できません。</span><span class="sxs-lookup"><span data-stu-id="47169-144">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="47169-145">さらに、情報バリア ポリシーに含まれているすべてのユーザーは、Microsoft Teams で他のユーザーと通信できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="47169-145">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="47169-146">情報バリア ポリシーの影響を受けるユーザーが同じチームまたはグループ チャットの一部である場合、それらのユーザーがチャット セッションから削除され、グループとのそれ以上の通信が許可されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="47169-146">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="47169-147">情報バリアに関するユーザー エクスペリエンスの詳細については [、「Microsoft Teams の情報バリア」を参照してください](/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="47169-147">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).</span></span>

<span data-ttu-id="47169-148">SharePoint Online および OneDrive では、情報バリア ポリシーによって、次の種類の未承認のコラボレーションが決定され、防止されます。</span><span class="sxs-lookup"><span data-stu-id="47169-148">In SharePoint Online and OneDrive, information barrier policies determine and prevent the following kinds of unauthorized collaborations:</span></span>

- <span data-ttu-id="47169-149">サイトへのメンバーの追加</span><span class="sxs-lookup"><span data-stu-id="47169-149">Adding a member to a site</span></span>
- <span data-ttu-id="47169-150">ユーザーによるサイトまたはコンテンツへのアクセス</span><span class="sxs-lookup"><span data-stu-id="47169-150">Accessing site or content by a user</span></span>
- <span data-ttu-id="47169-151">サイトまたはコンテンツを別のユーザーと共有する</span><span class="sxs-lookup"><span data-stu-id="47169-151">Sharing site or content with another user</span></span>
- <span data-ttu-id="47169-152">サイトの検索</span><span class="sxs-lookup"><span data-stu-id="47169-152">Searching a site</span></span>

<span data-ttu-id="47169-153">情報バリアに関するユーザー エクスペリエンスの詳細については、「SharePoint Online の情報バリア [」を参照してください。](/sharepoint/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="47169-153">To learn more about the user experience with information barriers, see [information barriers in SharePoint Online](/sharepoint/information-barriers)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="47169-154">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="47169-154">Required licenses and permissions</span></span>

<span data-ttu-id="47169-155">情報バリアは現在展開中で、次のようなサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="47169-155">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="47169-156">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="47169-156">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="47169-157">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="47169-157">Office 365 E5/A5</span></span>
- <span data-ttu-id="47169-158">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="47169-158">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="47169-159">Microsoft 365 コンプライアンス E5/A5</span><span class="sxs-lookup"><span data-stu-id="47169-159">Microsoft 365 Compliance E5/A5</span></span>
- <span data-ttu-id="47169-160">Microsoft 365 Insider リスク管理</span><span class="sxs-lookup"><span data-stu-id="47169-160">Microsoft 365 Insider Risk Management</span></span>

<span data-ttu-id="47169-161">詳細については [、「Microsoft 365 & ライセンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)ガイダンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47169-161">For more information, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

<span data-ttu-id="47169-162">情報 [バリア ポリシーを定義または編集するには](information-barriers-policies.md)、次のいずれかの役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="47169-162">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="47169-163">Microsoft 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="47169-163">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="47169-164">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="47169-164">Office 365 global administrator</span></span>
- <span data-ttu-id="47169-165">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="47169-165">Compliance administrator</span></span>
- <span data-ttu-id="47169-166">IB コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="47169-166">IB Compliance Management</span></span>

<span data-ttu-id="47169-167">(役割とアクセス許可の詳細については、「Office [365 Security](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md)& コンプライアンス センター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47169-167">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="47169-168">情報バリア ポリシーを定義、検証、または編集するには、PowerShell コマンドレットに精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="47169-168">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="47169-169">方法に関する記事では、PowerShell コマンドレットのいくつかの例[](information-barriers-policies.md)を示しますが、組織のパラメーターなど、他の詳細を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="47169-169">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know other details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47169-170">次のステップ</span><span class="sxs-lookup"><span data-stu-id="47169-170">Next steps</span></span>

- [<span data-ttu-id="47169-171">Microsoft Teams の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="47169-171">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="47169-172">SharePoint Online の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="47169-172">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="47169-173">OneDrive の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="47169-173">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="47169-174">情報バリア ポリシーに使用できる属性を確認する</span><span class="sxs-lookup"><span data-stu-id="47169-174">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="47169-175">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="47169-175">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="47169-176">情報バリア ポリシーの編集 (または削除)</span><span class="sxs-lookup"><span data-stu-id="47169-176">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)