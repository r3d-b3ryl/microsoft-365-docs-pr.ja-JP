---
title: メールユーザーをスタンドアロン EOP で管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: ディレクトリ同期、EAC、PowerShell を使用してユーザーを管理するなど、Exchange Online Protection (EOP) でメールユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e40465901747bcbd006d437fa527a9803aad1e24
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208647"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="239f4-103">メールユーザーをスタンドアロン EOP で管理する</span><span class="sxs-lookup"><span data-stu-id="239f4-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="239f4-104">Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、メールユーザーは基本的な種類のユーザーアカウントです。</span><span class="sxs-lookup"><span data-stu-id="239f4-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="239f4-105">メールユーザーは、スタンドアロンの EOP 組織内にアカウントの資格情報を持ち、リソースにアクセスできます (アクセス許可が割り当てられている)。</span><span class="sxs-lookup"><span data-stu-id="239f4-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="239f4-106">メールユーザーの電子メールアドレスが外部にある (たとえば、オンプレミスの電子メール環境で)。</span><span class="sxs-lookup"><span data-stu-id="239f4-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="239f4-107">メールユーザーを作成すると、対応するユーザーアカウントが Microsoft 365 管理センターで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="239f4-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="239f4-108">Microsoft 365 管理センターでユーザーアカウントを作成する場合、そのアカウントを使用してメールユーザーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="239f4-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="239f4-109">スタンドアロン EOP でメールユーザーを作成および管理するために推奨される方法は、このトピックで後述する「[ディレクトリ同期を使用してメールユーザーを管理する](#use-directory-synchronization-to-manage-mail-users)」の説明に従ってディレクトリ同期を使用することです。</span><span class="sxs-lookup"><span data-stu-id="239f4-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="239f4-110">ユーザー数が少ないスタンドアロンの EOP 組織では、このトピックで説明されているように、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell でメールユーザーを追加および管理できます。</span><span class="sxs-lookup"><span data-stu-id="239f4-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="239f4-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="239f4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="239f4-112">Exchange 管理センター (EAC) を開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="239f4-113">スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="239f4-114">EOP PowerShell でメールユーザーを作成するときに、調整が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="239f4-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="239f4-115">また、EOP PowerShell コマンドレットはバッチ処理方法を使用して、コマンドの結果が表示されるまでに数分の伝達遅延が発生するようになります。</span><span class="sxs-lookup"><span data-stu-id="239f4-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="239f4-116">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="239f4-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="239f4-117">具体的には、既定では、組織の管理 (グローバル管理者) および受信者管理役割グループに割り当てられているメール受信者作成 (作成) とメール受信者 (変更) の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="239f4-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="239f4-118">詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。</span><span class="sxs-lookup"><span data-stu-id="239f4-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="239f4-119">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="239f4-120">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="239f4-120">Having problems?</span></span> <span data-ttu-id="239f4-121">Exchange のフォーラムで質問してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="239f4-122">「 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="239f4-123">Exchange 管理センターを使用してメールユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="239f4-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="239f4-124">EAC を使用してメールユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="239f4-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="239f4-125">EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="239f4-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="239f4-126">[**新しい** ![ 新規作成] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="239f4-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="239f4-127">[**新しいメールユーザー** ] ページが開いたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="239f4-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="239f4-128">でマークされた設定 <sup>\*</sup> は必須です。</span><span class="sxs-lookup"><span data-stu-id="239f4-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="239f4-129">**名**</span><span class="sxs-lookup"><span data-stu-id="239f4-129">**First name**</span></span>

   - <span data-ttu-id="239f4-130">**イニシャル**: ユーザーのミドルネームのイニシャル。</span><span class="sxs-lookup"><span data-stu-id="239f4-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="239f4-131">**姓**</span><span class="sxs-lookup"><span data-stu-id="239f4-131">**Last name**</span></span>

   - <span data-ttu-id="239f4-132"><sup>\*</sup>[**表示名**]: 既定では、このボックスには、[**名**]、[**イニシャル**]、[**姓**] ボックスの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="239f4-133">この値を受け入れるか、または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="239f4-133">You can accept this value or change it.</span></span> <span data-ttu-id="239f4-134">この値は一意である必要があり、最大長は64文字です。</span><span class="sxs-lookup"><span data-stu-id="239f4-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="239f4-135"><sup>\*</sup>**エイリアス**: ユーザーに対して、最大64文字の一意のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="239f4-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="239f4-136">**外部電子メールアドレス**: ユーザーの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="239f4-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="239f4-137">ドメインは、クラウドベースの組織の外部にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="239f4-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="239f4-138"><sup>\*</sup>**ユーザー ID**: ユーザーがサービスにサインインするために使用するアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="239f4-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="239f4-139">ユーザー ID は、アットマーク記号 (@) の左側のユーザー名と右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="239f4-140"><sup>\*</sup>[**新しいパスワード**] と [ <sup>\*</sup> **パスワードの確認**]: アカウントのパスワードを入力して再入力します。</span><span class="sxs-lookup"><span data-stu-id="239f4-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="239f4-141">パスワードが組織のパスワードの長さ、複雑さ、および履歴に関する要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="239f4-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="239f4-142">完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="239f4-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="239f4-143">EAC を使用してメールユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="239f4-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="239f4-144">EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="239f4-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="239f4-145">変更するメールユーザーを選択し、[編集アイコンの**編集**] をクリックし ![ ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="239f4-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="239f4-146">開いたメールユーザーのプロパティページで、次のタブのいずれかをクリックして、プロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="239f4-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="239f4-147">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="239f4-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="239f4-148">全般</span><span class="sxs-lookup"><span data-stu-id="239f4-148">General</span></span>

<span data-ttu-id="239f4-149">**[全般**] タブを使用して、メールユーザーの基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="239f4-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="239f4-150">**名**</span><span class="sxs-lookup"><span data-stu-id="239f4-150">**First name**</span></span>

- <span data-ttu-id="239f4-151">**頭文字**</span><span class="sxs-lookup"><span data-stu-id="239f4-151">**Initials**</span></span>

- <span data-ttu-id="239f4-152">**姓**</span><span class="sxs-lookup"><span data-stu-id="239f4-152">**Last name**</span></span>

- <span data-ttu-id="239f4-153">[**表示名**]: この名前は、組織のアドレス帳、電子メールの宛先行と差出人行、および EAC 内の連絡先の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="239f4-154">この名前は、表示名の前または後に空のスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="239f4-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="239f4-155">**ユーザー ID**: これは、Microsoft 365 のユーザーアカウントです。</span><span class="sxs-lookup"><span data-stu-id="239f4-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="239f4-156">ここでは、この値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="239f4-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="239f4-157">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="239f4-157">Contact information</span></span>

<span data-ttu-id="239f4-158">[**連絡先の情報**] タブを使用して、ユーザーの連絡先情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="239f4-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="239f4-159">このページの情報がアドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="239f4-160">**所在**</span><span class="sxs-lookup"><span data-stu-id="239f4-160">**Street**</span></span>
- <span data-ttu-id="239f4-161">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="239f4-161">**City**</span></span>
- <span data-ttu-id="239f4-162">**都道府県**</span><span class="sxs-lookup"><span data-stu-id="239f4-162">**State/Province**</span></span>
- <span data-ttu-id="239f4-163">**郵便番号**</span><span class="sxs-lookup"><span data-stu-id="239f4-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="239f4-164">**国/地域設定**</span><span class="sxs-lookup"><span data-stu-id="239f4-164">**Country/Region**</span></span>
- <span data-ttu-id="239f4-165">**勤務先の電話番号**</span><span class="sxs-lookup"><span data-stu-id="239f4-165">**Work phone**</span></span>
- <span data-ttu-id="239f4-166">**携帯電話**</span><span class="sxs-lookup"><span data-stu-id="239f4-166">**Mobile phone**</span></span>
- <span data-ttu-id="239f4-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="239f4-167">**Fax**</span></span>
- <span data-ttu-id="239f4-168">**[その他のオプション]**</span><span class="sxs-lookup"><span data-stu-id="239f4-168">**More options**</span></span>

  - <span data-ttu-id="239f4-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="239f4-169">**Office**</span></span>
  - <span data-ttu-id="239f4-170">**自宅電話**</span><span class="sxs-lookup"><span data-stu-id="239f4-170">**Home phone**</span></span>
  - <span data-ttu-id="239f4-171">**Web ページ**</span><span class="sxs-lookup"><span data-stu-id="239f4-171">**Web page**</span></span>
  - <span data-ttu-id="239f4-172">**メモ**</span><span class="sxs-lookup"><span data-stu-id="239f4-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="239f4-173">組織</span><span class="sxs-lookup"><span data-stu-id="239f4-173">Organization</span></span>

<span data-ttu-id="239f4-174">[**組織**] タブを使用して、組織内のユーザーの役割に関する詳細情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="239f4-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="239f4-175">**役職**</span><span class="sxs-lookup"><span data-stu-id="239f4-175">**Title**</span></span>
- <span data-ttu-id="239f4-176">**部署**</span><span class="sxs-lookup"><span data-stu-id="239f4-176">**Department**</span></span>
- <span data-ttu-id="239f4-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="239f4-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="239f4-178">EAC を使用してメールユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="239f4-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="239f4-179">EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="239f4-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="239f4-180">削除するメールユーザーを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="239f4-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="239f4-181">PowerShell を使用してメールユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="239f4-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="239f4-182">スタンドアロンの EOP PowerShell を使用してメールユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="239f4-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="239f4-183">スタンドアロン EOP PowerShell のすべてのメールユーザーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="239f4-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="239f4-184">特定のメールユーザーについての詳細情報を表示するには、 \< mailuseridentity を \> メールユーザーの名前、エイリアス、またはアカウント名に置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="239f4-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="239f4-185">構文およびパラメーターの詳細については、「[取得-受信者](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)と[取得ユーザー](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="239f4-186">スタンドアロンの EOP PowerShell を使用してメールユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="239f4-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="239f4-187">スタンドアロン EOP PowerShell でメールユーザーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="239f4-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="239f4-188">**注**:</span><span class="sxs-lookup"><span data-stu-id="239f4-188">**Notes**:</span></span>

- <span data-ttu-id="239f4-189">_Name_パラメーターは必須で、最大長は64文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="239f4-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="239f4-190">_DisplayName_パラメーターを使用しない場合、 _name_パラメーターの値が表示名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="239f4-191">_Alias_パラメーターを使用しない場合、 _MicrosoftOnlneServicesID_パラメーターの左側がエイリアスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlneServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="239f4-192">_ExternalEmailAddress_パラメーターを使用しない場合、 _MicrosoftOnlineServicesID_の値が外部の電子メールアドレスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="239f4-193">この例では、次の設定を使用してメールユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="239f4-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="239f4-194">名前は JeffreyZeng で、表示名は Jeffrey Zeng です。</span><span class="sxs-lookup"><span data-stu-id="239f4-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="239f4-195">名は Jeffrey で、姓は Zeng です。</span><span class="sxs-lookup"><span data-stu-id="239f4-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="239f4-196">エイリアスは jeffreyz です。</span><span class="sxs-lookup"><span data-stu-id="239f4-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="239f4-197">外部の電子メール アドレスは jzeng@tailspintoys.com です。</span><span class="sxs-lookup"><span data-stu-id="239f4-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="239f4-198">アカウント名は jeffreyz@contoso.onmicrosoft.com です。</span><span class="sxs-lookup"><span data-stu-id="239f4-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="239f4-199">パスワードは Pa$$word1 です。</span><span class="sxs-lookup"><span data-stu-id="239f4-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="239f4-200">構文およびパラメーターの詳細については、「 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="239f4-201">スタンドアロンの EOP PowerShell を使用してメールユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="239f4-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="239f4-202">スタンドアロン EOP PowerShell で既存のメールユーザーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="239f4-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="239f4-203">この例では、Pilar Pinilla の外部電子メール アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="239f4-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="239f4-204">この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="239f4-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="239f4-205">構文およびパラメーターの詳細については、「 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="239f4-206">スタンドアロンの EOP PowerShell を使用してメールユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="239f4-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="239f4-207">スタンドアロン EOP PowerShell でメールユーザーを削除するには、 \< mailuseridentity を \> メールユーザーの名前、エイリアス、またはアカウント名に置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="239f4-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="239f4-208">この例では、Jeffrey Zeng のメールユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="239f4-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="239f4-209">構文およびパラメーターの詳細については、「 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="239f4-210">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="239f4-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="239f4-211">メールユーザーの作成、変更、または削除が正常に完了したことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="239f4-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="239f4-212">EAC で、[受信者の**Recipients** \> **連絡先**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="239f4-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="239f4-213">メールユーザーが一覧に表示されている (または一覧に表示されていない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="239f4-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="239f4-214">メールユーザーを選択して、詳細ウィンドウに情報を表示するか、[編集アイコンの**編集**] をクリックして ![ 設定を表示し ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="239f4-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="239f4-215">スタンドアロン EOP PowerShell で、次のコマンドを実行して、メールユーザーが一覧に表示されている (または一覧に表示されていない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="239f4-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="239f4-216">\<Mailuseridentity を \> メールユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="239f4-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="239f4-217">ディレクトリ同期を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="239f4-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="239f4-218">スタンドアロン EOP では、オンプレミスの Active Directory を使用しているお客様はディレクトリ同期を利用できます。</span><span class="sxs-lookup"><span data-stu-id="239f4-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="239f4-219">これらのアカウントを Azure Active Directory (Azure AD) と同期することができます。これにより、アカウントのコピーがクラウドに保存されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="239f4-220">既存のユーザーアカウントを Azure Active Directory と同期する場合は、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell の [**受信者**] ウィンドウで、これらのユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="239f4-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="239f4-221">**注**:</span><span class="sxs-lookup"><span data-stu-id="239f4-221">**Notes**:</span></span>

- <span data-ttu-id="239f4-222">ディレクトリ同期を使用して受信者を管理している場合でも、Microsoft 365 管理センターでユーザーを追加および管理することはできますが、オンプレミスの Active Directory と同期されることはありません。</span><span class="sxs-lookup"><span data-stu-id="239f4-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="239f4-223">これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="239f4-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="239f4-224">次の機能によるディレクトリ同期の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="239f4-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="239f4-225">**Outlook の差出人セーフリストと受信拒否リスト**: サービスに同期すると、これらのリストはサービスのスパムフィルタリングよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="239f4-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="239f4-226">これにより、ユーザーは、個々の送信者およびドメインエントリを使用して、自分の差出人セーフリストと受信拒否リストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="239f4-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="239f4-227">詳細については、「 [Exchange Online メールボックスで迷惑メールの設定を構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="239f4-228">**ディレクトリベースのエッジブロック (dbeb)**: DBEB の詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="239f4-229">**エンドユーザーによる検疫へのアクセス**: 検疫されたメッセージにアクセスするには、受信者がサービスに有効なユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="239f4-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="239f4-230">検疫の詳細については、「[ユーザーとして検疫済みメッセージを検索して解放する](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="239f4-231">**メールフロールール (トランスポートルールとも呼ばれる)**: ディレクトリ同期を使用すると、既存の Active directory ユーザーとグループがクラウドに自動的にアップロードされます。その後、特定のユーザーやグループを対象とするメールフロールールを作成して、それらをサービスに手動で追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="239f4-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="239f4-232">[動的配布グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)はディレクトリ同期を使用して同期できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="239f4-233">必要なアクセス許可を取得し、ディレクトリ同期を準備します (「 [Azure Active directory でのハイブリッド id とは](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="239f4-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="239f4-234">ディレクトリを Azure Active Directory Connect (AAD Connect) と同期する</span><span class="sxs-lookup"><span data-stu-id="239f4-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="239f4-235">「 [AZURE AD Connect 同期: 同期の理解とカスタマイズ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)」の説明に従って、ディレクトリ同期をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="239f4-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="239f4-236">[AZURE AD Connect の前提条件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)に従って、AAD Connect を実行するようにオンプレミスのコンピューターをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="239f4-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="239f4-237">[AZURE AD Connect に使用するインストールの種類を選択し](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)ます。</span><span class="sxs-lookup"><span data-stu-id="239f4-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="239f4-238">ニュース</span><span class="sxs-lookup"><span data-stu-id="239f4-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="239f4-239">Custom</span><span class="sxs-lookup"><span data-stu-id="239f4-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="239f4-240">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="239f4-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="239f4-p121">Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="239f4-244">同期を構成した後、AAD Connect が正しく同期されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="239f4-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="239f4-245">EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="239f4-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
