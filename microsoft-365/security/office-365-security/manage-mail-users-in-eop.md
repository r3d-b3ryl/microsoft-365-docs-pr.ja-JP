---
title: スタンドアロン EOP でメール ユーザーを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: ディレクトリ同期、EAC、PowerShell を使用してユーザーを管理するExchange Online Protection (EOP) でメール ユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205046"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="b684f-103">スタンドアロン EOP でメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="b684f-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b684f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="b684f-104">**Applies to**</span></span>
-  [<span data-ttu-id="b684f-105">Exchange Online Protectionスタンドアロン</span><span class="sxs-lookup"><span data-stu-id="b684f-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="b684f-106">メールボックスをExchange Online Protectionスタンドアロン Exchange Online (EOP) 組織では、メール ユーザーは基本的な種類のユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="b684f-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="b684f-107">メール ユーザーは、スタンドアロンの EOP 組織にアカウント資格情報を持ち、リソースにアクセスできます (アクセス許可が割り当て済み)。</span><span class="sxs-lookup"><span data-stu-id="b684f-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="b684f-108">メール ユーザーの電子メール アドレスは外部 (オンプレミスのメール環境など) です。</span><span class="sxs-lookup"><span data-stu-id="b684f-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="b684f-109">メール ユーザーを作成すると、対応するユーザー アカウントが管理センター Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b684f-110">管理センターでユーザー アカウントをMicrosoft 365、そのアカウントを使用してメール ユーザーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="b684f-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="b684f-111">スタンドアロン EOP でメール ユーザーを作成および管理する推奨される方法は、この記事の[](#use-directory-synchronization-to-manage-mail-users)後半の「ディレクトリ同期を使用してメール ユーザーを管理する」セクションで説明されているディレクトリ同期を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="b684f-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="b684f-112">ユーザー数が少ないスタンドアロン EOP 組織では、この記事で説明するように、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell でメール ユーザーを追加および管理できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b684f-113">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="b684f-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b684f-114">管理センター (EAC Exchange開く場合は、「スタンドアロン[EOP Exchange管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="b684f-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b684f-115">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b684f-116">EOP PowerShell でメール ユーザーを作成すると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b684f-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="b684f-117">また、EOP PowerShell コマンドレットはバッチ処理メソッドを使用して、コマンドの結果が表示される数分前に伝達遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="b684f-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b684f-118">この記事の手順を実行するには、Exchange Online Protectionにアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b684f-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="b684f-119">具体的には、既定で組織 **管理 (グローバル** 管理者) および受信者管理役割グループに割り当てられているメール受信者の **作成 (作成**) およびメール受信者 **(変更**) の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="b684f-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="b684f-120">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="b684f-121">この記事の手順 Exchangeに適用されるキーボード ショートカットの詳細については、「Exchange Online の管理センターのキーボード ショートカット」[を参照Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="b684f-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b684f-122">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="b684f-122">Having problems?</span></span> <span data-ttu-id="b684f-123">Exchange のフォーラムで質問してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="b684f-124">[ユーザー][フォーラムExchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)アクセスします。</span><span class="sxs-lookup"><span data-stu-id="b684f-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="b684f-125">メール ユーザーを管理Exchange管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="b684f-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="b684f-126">EAC を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="b684f-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="b684f-127">EAC で、[受信者の **連絡先] に移動** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="b684f-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="b684f-128">[新 **しい新規]** ![ アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) します。</span><span class="sxs-lookup"><span data-stu-id="b684f-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="b684f-129">開く **[新しいメール ユーザー]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b684f-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="b684f-130"><sup>\*</sup> の付いた設定は必須項目です。</span><span class="sxs-lookup"><span data-stu-id="b684f-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="b684f-131">**名**</span><span class="sxs-lookup"><span data-stu-id="b684f-131">**First name**</span></span>

   - <span data-ttu-id="b684f-132">**イニシャル**: ユーザーの中間イニシャル。</span><span class="sxs-lookup"><span data-stu-id="b684f-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="b684f-133">**姓**</span><span class="sxs-lookup"><span data-stu-id="b684f-133">**Last name**</span></span>

   - <span data-ttu-id="b684f-134"><sup>\*</sup>**表示名**: 既定では、このボックスには、名、イニシャル、および名の **各ボックスの値が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="b684f-135">この値を受け入れるか、変更できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-135">You can accept this value or change it.</span></span> <span data-ttu-id="b684f-136">値は一意で、最大長は 64 文字です。</span><span class="sxs-lookup"><span data-stu-id="b684f-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="b684f-137"><sup>\*</sup>**Alias**: ユーザーに対して最大 64 文字を使用して、一意のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b684f-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="b684f-138">**外部メール アドレス**: ユーザーの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b684f-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="b684f-139">ドメインはクラウドベースの組織の外部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b684f-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="b684f-140"><sup>\*</sup>**ユーザー ID:** ユーザーがサービスへのサインインに使用するアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="b684f-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="b684f-141">ユーザー ID は、at (@) 記号 (@) の左側のユーザー名と右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="b684f-142"><sup>\*</sup>**新しいパスワード** <sup>\*</sup> **とパスワードの確認**: アカウント のパスワードを入力して再入力します。</span><span class="sxs-lookup"><span data-stu-id="b684f-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="b684f-143">パスワードが組織のパスワードの長さ、複雑さ、および履歴の要件に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b684f-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="b684f-144">完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b684f-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="b684f-145">EAC を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="b684f-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="b684f-146">EAC で、[受信者の連絡先 **] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="b684f-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="b684f-147">変更するメール ユーザーを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="b684f-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="b684f-148">開くメール ユーザーのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="b684f-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="b684f-149">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b684f-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="b684f-150">全般</span><span class="sxs-lookup"><span data-stu-id="b684f-150">General</span></span>

<span data-ttu-id="b684f-151">[全般] **タブ** を使用して、メール ユーザーに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="b684f-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="b684f-152">**名**</span><span class="sxs-lookup"><span data-stu-id="b684f-152">**First name**</span></span>

- <span data-ttu-id="b684f-153">**頭文字**</span><span class="sxs-lookup"><span data-stu-id="b684f-153">**Initials**</span></span>

- <span data-ttu-id="b684f-154">**姓**</span><span class="sxs-lookup"><span data-stu-id="b684f-154">**Last name**</span></span>

- <span data-ttu-id="b684f-155">**表示名**: この名前は、組織のアドレス帳、電子メールの [To:] 行と [From:] 行、および EAC の連絡先の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="b684f-156">この名前は、表示名の前または後に空のスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b684f-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="b684f-157">**ユーザー ID**: このアカウントは、ユーザーのアカウントMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="b684f-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="b684f-158">この値はここで変更できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="b684f-159">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="b684f-159">Contact information</span></span>

<span data-ttu-id="b684f-160">[連絡先情報 **] タブを** 使用して、ユーザーの連絡先情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="b684f-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="b684f-161">このページの情報がアドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="b684f-162">**Street**</span><span class="sxs-lookup"><span data-stu-id="b684f-162">**Street**</span></span>
- <span data-ttu-id="b684f-163">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="b684f-163">**City**</span></span>
- <span data-ttu-id="b684f-164">**都道府県**</span><span class="sxs-lookup"><span data-stu-id="b684f-164">**State/Province**</span></span>
- <span data-ttu-id="b684f-165">**郵便番号**</span><span class="sxs-lookup"><span data-stu-id="b684f-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="b684f-166">**国/地域設定**</span><span class="sxs-lookup"><span data-stu-id="b684f-166">**Country/Region**</span></span>
- <span data-ttu-id="b684f-167">**勤務先の電話番号**</span><span class="sxs-lookup"><span data-stu-id="b684f-167">**Work phone**</span></span>
- <span data-ttu-id="b684f-168">**携帯電話**</span><span class="sxs-lookup"><span data-stu-id="b684f-168">**Mobile phone**</span></span>
- <span data-ttu-id="b684f-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="b684f-169">**Fax**</span></span>
- <span data-ttu-id="b684f-170">**[その他のオプション]**</span><span class="sxs-lookup"><span data-stu-id="b684f-170">**More options**</span></span>

  - <span data-ttu-id="b684f-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="b684f-171">**Office**</span></span>
  - <span data-ttu-id="b684f-172">**自宅電話**</span><span class="sxs-lookup"><span data-stu-id="b684f-172">**Home phone**</span></span>
  - <span data-ttu-id="b684f-173">**Web ページ**</span><span class="sxs-lookup"><span data-stu-id="b684f-173">**Web page**</span></span>
  - <span data-ttu-id="b684f-174">**注**</span><span class="sxs-lookup"><span data-stu-id="b684f-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="b684f-175">組織</span><span class="sxs-lookup"><span data-stu-id="b684f-175">Organization</span></span>

<span data-ttu-id="b684f-176">[組織 **] タブ** を使用して、組織内のユーザーの役割に関する詳細情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="b684f-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="b684f-177">**役職**</span><span class="sxs-lookup"><span data-stu-id="b684f-177">**Title**</span></span>
- <span data-ttu-id="b684f-178">**部署**</span><span class="sxs-lookup"><span data-stu-id="b684f-178">**Department**</span></span>
- <span data-ttu-id="b684f-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="b684f-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="b684f-180">EAC を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="b684f-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="b684f-181">EAC で、[受信者の連絡先 **] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="b684f-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="b684f-182">削除するメール ユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="b684f-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="b684f-183">PowerShell を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="b684f-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="b684f-184">スタンドアロン EOP PowerShell を使用してメール ユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="b684f-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="b684f-185">スタンドアロン EOP PowerShell のすべてのメール ユーザーの概要リストを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b684f-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="b684f-186">特定のメール ユーザーに関する詳細情報を表示するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換えて、次の \<MailUserIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b684f-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="b684f-187">構文とパラメーターの詳細については [、「Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User」を参照してください](/powershell/module/exchange/get-user)。</span><span class="sxs-lookup"><span data-stu-id="b684f-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="b684f-188">スタンドアロン EOP PowerShell を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="b684f-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="b684f-189">スタンドアロン EOP PowerShell でメール ユーザーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b684f-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="b684f-190">**注**:</span><span class="sxs-lookup"><span data-stu-id="b684f-190">**Notes**:</span></span>

- <span data-ttu-id="b684f-191">_Name パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b684f-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="b684f-192">DisplayName パラメーターを使用しない場合は _、Name_ パラメーターの値が表示名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="b684f-193">_Alias_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ パラメーターの左側がエイリアスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="b684f-194">_ExternalEmailAddress_ パラメーターを使用しない場合は、外部メール アドレスに _MicrosoftOnlineServicesID_ 値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="b684f-195">この例では、次の設定を使用してメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b684f-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="b684f-196">名前は JeffreyZeng で、表示名は Jeffrey Zeng です。</span><span class="sxs-lookup"><span data-stu-id="b684f-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="b684f-197">名は Jeffrey で、姓は Zeng です。</span><span class="sxs-lookup"><span data-stu-id="b684f-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="b684f-198">エイリアスは jeffreyz です。</span><span class="sxs-lookup"><span data-stu-id="b684f-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="b684f-199">外部の電子メール アドレスは jzeng@tailspintoys.com です。</span><span class="sxs-lookup"><span data-stu-id="b684f-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="b684f-200">アカウント名は jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="b684f-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="b684f-201">パスワードは Pa$$word1 です。</span><span class="sxs-lookup"><span data-stu-id="b684f-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="b684f-202">構文とパラメーターの詳細については [、「New-EOPMailUser」を参照してください](/powershell/module/exchange/new-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="b684f-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="b684f-203">スタンドアロン EOP PowerShell を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="b684f-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="b684f-204">スタンドアロン EOP PowerShell の既存のメール ユーザーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b684f-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="b684f-205">この例では、Pilar Pinilla の外部電子メール アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="b684f-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="b684f-206">この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="b684f-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="b684f-207">構文とパラメーターの詳細については [、「Set-EOPMailUser」を参照してください](/powershell/module/exchange/set-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="b684f-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="b684f-208">スタンドアロン EOP PowerShell を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="b684f-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="b684f-209">スタンドアロン EOP PowerShell でメール ユーザーを削除するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次の \<MailUserIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b684f-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="b684f-210">この例では、Jeffrey Zeng のメール ユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b684f-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="b684f-211">構文とパラメーターの詳細については [、「Remove-EOPMailUser」を参照してください](/powershell/module/exchange/remove-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="b684f-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b684f-212">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b684f-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="b684f-213">スタンドアロン EOP でメール ユーザーが正常に作成、変更、または削除されたことを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b684f-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="b684f-214">EAC で、[受信者の連絡先 **] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="b684f-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="b684f-215">メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。</span><span class="sxs-lookup"><span data-stu-id="b684f-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="b684f-216">メール ユーザーを選択し、[詳細] ウィンドウで情報を表示するか、[ **編集]** アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-AddIcon.png) を表示します。</span><span class="sxs-lookup"><span data-stu-id="b684f-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="b684f-217">スタンドアロン EOP PowerShell で、次のコマンドを実行して、メール ユーザーが一覧に表示されている (または一覧に表示されていない) のを確認します。</span><span class="sxs-lookup"><span data-stu-id="b684f-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="b684f-218">メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して設定 \<MailUserIdentity\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="b684f-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="b684f-219">ディレクトリ同期を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="b684f-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="b684f-220">スタンドアロン EOP では、オンプレミスの Active Directory をお持ちのお客様にディレクトリ同期を利用できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="b684f-221">これらのアカウントをクラウドにAzure Active Directory (Azure AD) に同期できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="b684f-222">既存のユーザー アカウントを Azure Active Directory に同期すると、それらのユーザーを Exchange 管理センター  (EAC) の [受信者] ウィンドウまたはスタンドアロンの EOP PowerShell で表示できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="b684f-223">**注**:</span><span class="sxs-lookup"><span data-stu-id="b684f-223">**Notes**:</span></span>

- <span data-ttu-id="b684f-224">ディレクトリ同期を使用して受信者を管理する場合でも、Microsoft 365 管理センターでユーザーを追加および管理できますが、ユーザーはオンプレミスの Active Directory と同期されません。</span><span class="sxs-lookup"><span data-stu-id="b684f-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="b684f-225">これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="b684f-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="b684f-226">次の機能によるディレクトリ同期の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b684f-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="b684f-227">**Outlook セーフ送信者リスト** と受信拒否リスト : サービスに同期すると、これらのリストはサービスのスパム フィルター処理よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b684f-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="b684f-228">これにより、ユーザーは個々の送信者とセーフを使用して、送信者リストと受信拒否リストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="b684f-229">詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="b684f-230">**ディレクトリ ベースのエッジ ブロック (DBEB)**: DBEB の詳細については、「Use Directory Based Edge Blocking to [reject messages to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="b684f-231">**検疫へのエンド ユーザー アクセス**: 検疫済みメッセージにアクセスするには、受信者がサービスに有効なユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b684f-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="b684f-232">検疫の詳細については、「検疫済みメッセージをユーザーとして検索 [して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="b684f-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="b684f-233">**メール フロー** ルール (トランスポート ルールとも呼ばれる) : ディレクトリ同期を使用すると、既存の Active Directory ユーザーとグループがクラウドに自動的にアップロードされ、サービスに手動で追加することなく、特定のユーザーまたはグループを対象とするメール フロー ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b684f-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="b684f-234">動的配布 [グループはディレクトリ](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 同期では同期できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="b684f-235">必要なアクセス許可を取得し、ディレクトリ同期の準備を行います(「ハイブリッド ID とハイブリッド ID は何ですか[Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity)</span><span class="sxs-lookup"><span data-stu-id="b684f-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="b684f-236">ディレクトリを Azure Active Directory Connectと同期する (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="b684f-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="b684f-237">Azure の同期の説明に従ってディレクトリ[同期AD Connect同期を確認し、カスタマイズします](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="b684f-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="b684f-238">「Azure の前提条件」の説明に従って、AAD Connectを実行するようにオンプレミス コンピューターをインストールして[構成AD Connect。](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="b684f-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="b684f-239">[Azure アプリケーションで使用するインストールの種類を選択AD Connect。](/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="b684f-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="b684f-240">Express</span><span class="sxs-lookup"><span data-stu-id="b684f-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="b684f-241">Custom</span><span class="sxs-lookup"><span data-stu-id="b684f-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="b684f-242">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="b684f-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="b684f-p121">Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="b684f-246">同期を構成したら、AAD が正しく同期Connect確認してください。</span><span class="sxs-lookup"><span data-stu-id="b684f-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="b684f-247">EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b684f-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>