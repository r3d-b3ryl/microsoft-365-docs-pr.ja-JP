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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: ディレクトリ同期、EAC、PowerShell を使用してユーザーを管理する方法など、Exchange Online Protection (EOP) でメール ユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658835"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="380fb-103">スタンドアロン EOP でメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="380fb-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="380fb-104">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、メール ユーザーは基本的な種類のユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="380fb-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="380fb-105">メール ユーザーは、スタンドアロン EOP 組織のアカウント資格情報を持ち、リソースにアクセスできます (アクセス許可が割り当てられている)。</span><span class="sxs-lookup"><span data-stu-id="380fb-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="380fb-106">メール ユーザーの電子メール アドレスは外部 (たとえば、オンプレミスのメール環境) です。</span><span class="sxs-lookup"><span data-stu-id="380fb-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="380fb-107">メール ユーザーを作成すると、対応するユーザー アカウントが Microsoft 365 管理センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="380fb-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="380fb-108">Microsoft 365 管理センターでユーザー アカウントを作成する場合、そのアカウントを使用してメール ユーザーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="380fb-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="380fb-109">スタンドアロン EOP でメール ユーザーを作成および管理するには、この記事で後述する「ディレクトリ[](#use-directory-synchronization-to-manage-mail-users)同期を使用してメール ユーザーを管理する」セクションで説明するように、ディレクトリ同期を使用する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="380fb-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="380fb-110">ユーザー数が少ないスタンドアロン EOP 組織の場合は、この記事で説明するように、Exchange 管理センター (EAC) またはスタンドアロンの EOP PowerShell でメール ユーザーを追加および管理できます。</span><span class="sxs-lookup"><span data-stu-id="380fb-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="380fb-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="380fb-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="380fb-112">Exchange 管理センター (EAC) を開く方法については、スタンドアロン EOP の [Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="380fb-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="380fb-113">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380fb-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="380fb-114">EOP PowerShell でメール ユーザーを作成すると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="380fb-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="380fb-115">また、EOP PowerShell コマンドレットはバッチ処理方法を使用して、コマンドの結果が表示される数分前に伝達遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="380fb-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="380fb-116">この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="380fb-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="380fb-117">具体的には、既定で組織の管理 **(グローバル** 管理者) 役割グループと受信者管理役割グループに割り当てられる、メール受信者の作成 **(** 作成) 役割とメール受信者 **(変更**) 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="380fb-117">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="380fb-118">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="380fb-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="380fb-119">この記事の手順に適用できるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="380fb-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="380fb-120">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="380fb-120">Having problems?</span></span> <span data-ttu-id="380fb-121">Exchange のフォーラムで質問してください。</span><span class="sxs-lookup"><span data-stu-id="380fb-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="380fb-122">Exchange [Online Protection フォーラムにアクセス](https://go.microsoft.com/fwlink/p/?linkId=285351) します。</span><span class="sxs-lookup"><span data-stu-id="380fb-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="380fb-123">Exchange 管理センターを使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="380fb-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="380fb-124">EAC を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="380fb-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="380fb-125">EAC で、受信者の **連絡先に移動** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="380fb-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="380fb-126">[新 **しい新規]** ![ アイコンをクリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="380fb-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="380fb-127">開く **[新しいメール ユーザー** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="380fb-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="380fb-128">an が付いている設定 <sup>\*</sup> は必須です。</span><span class="sxs-lookup"><span data-stu-id="380fb-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="380fb-129">**名**</span><span class="sxs-lookup"><span data-stu-id="380fb-129">**First name**</span></span>

   - <span data-ttu-id="380fb-130">**イニシャル**: 人物の中間イニシャル。</span><span class="sxs-lookup"><span data-stu-id="380fb-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="380fb-131">**姓**</span><span class="sxs-lookup"><span data-stu-id="380fb-131">**Last name**</span></span>

   - <span data-ttu-id="380fb-132"><sup>\*</sup>**表示名**: 既定では、このボックスには [名]、[イニシャル]、および [氏名] ボックス **の値が** 表示されます。 </span><span class="sxs-lookup"><span data-stu-id="380fb-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="380fb-133">この値を受け入れるか、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="380fb-133">You can accept this value or change it.</span></span> <span data-ttu-id="380fb-134">値は一意で、最大長は 64 文字です。</span><span class="sxs-lookup"><span data-stu-id="380fb-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="380fb-135"><sup>\*</sup>**エイリアス**: ユーザーに対して最大 64 文字を使用して一意のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="380fb-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="380fb-136">**外部電子メール アドレス**: ユーザーの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="380fb-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="380fb-137">ドメインはクラウドベースの組織の外部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="380fb-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="380fb-138"><sup>\*</sup>**ユーザー ID**: ユーザーがサービスにサインインするために使用するアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="380fb-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="380fb-139">ユーザー ID は、at (@) 記号 (@) の左側のユーザー名と右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="380fb-140"><sup>\*</sup>**新しいパスワード** と <sup>\*</sup> **パスワードの確認**: アカウントパスワードを入力して再入力します。</span><span class="sxs-lookup"><span data-stu-id="380fb-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="380fb-141">パスワードが組織のパスワードの長さ、複雑さ、履歴の要件に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="380fb-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="380fb-142">完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="380fb-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="380fb-143">EAC を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="380fb-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="380fb-144">EAC で、受信者の連絡先 **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="380fb-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="380fb-145">変更するメール ユーザーを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="380fb-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="380fb-146">表示されたメール ユーザーのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="380fb-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="380fb-147">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="380fb-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="380fb-148">全般</span><span class="sxs-lookup"><span data-stu-id="380fb-148">General</span></span>

<span data-ttu-id="380fb-149">[全般 **] タブを** 使用して、メール ユーザーに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="380fb-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="380fb-150">**名**</span><span class="sxs-lookup"><span data-stu-id="380fb-150">**First name**</span></span>

- <span data-ttu-id="380fb-151">**頭文字**</span><span class="sxs-lookup"><span data-stu-id="380fb-151">**Initials**</span></span>

- <span data-ttu-id="380fb-152">**姓**</span><span class="sxs-lookup"><span data-stu-id="380fb-152">**Last name**</span></span>

- <span data-ttu-id="380fb-153">**表示名**: この名前は、組織のアドレス帳、電子メールの [To:] 行と [From:] 行、および EAC の連絡先の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="380fb-154">この名前は、表示名の前または後に空のスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="380fb-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="380fb-155">**ユーザー ID**: Microsoft 365 のユーザーのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="380fb-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="380fb-156">この値はここで変更できます。</span><span class="sxs-lookup"><span data-stu-id="380fb-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="380fb-157">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="380fb-157">Contact information</span></span>

<span data-ttu-id="380fb-158">[連絡先情報 **] タブを** 使用して、ユーザーの連絡先情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="380fb-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="380fb-159">このページの情報がアドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="380fb-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="380fb-160">**Street**</span></span>
- <span data-ttu-id="380fb-161">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="380fb-161">**City**</span></span>
- <span data-ttu-id="380fb-162">**都道府県**</span><span class="sxs-lookup"><span data-stu-id="380fb-162">**State/Province**</span></span>
- <span data-ttu-id="380fb-163">**郵便番号**</span><span class="sxs-lookup"><span data-stu-id="380fb-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="380fb-164">**国/地域設定**</span><span class="sxs-lookup"><span data-stu-id="380fb-164">**Country/Region**</span></span>
- <span data-ttu-id="380fb-165">**勤務先の電話番号**</span><span class="sxs-lookup"><span data-stu-id="380fb-165">**Work phone**</span></span>
- <span data-ttu-id="380fb-166">**携帯電話**</span><span class="sxs-lookup"><span data-stu-id="380fb-166">**Mobile phone**</span></span>
- <span data-ttu-id="380fb-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="380fb-167">**Fax**</span></span>
- <span data-ttu-id="380fb-168">**[その他のオプション]**</span><span class="sxs-lookup"><span data-stu-id="380fb-168">**More options**</span></span>

  - <span data-ttu-id="380fb-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="380fb-169">**Office**</span></span>
  - <span data-ttu-id="380fb-170">**自宅電話**</span><span class="sxs-lookup"><span data-stu-id="380fb-170">**Home phone**</span></span>
  - <span data-ttu-id="380fb-171">**Web ページ**</span><span class="sxs-lookup"><span data-stu-id="380fb-171">**Web page**</span></span>
  - <span data-ttu-id="380fb-172">**注**</span><span class="sxs-lookup"><span data-stu-id="380fb-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="380fb-173">組織</span><span class="sxs-lookup"><span data-stu-id="380fb-173">Organization</span></span>

<span data-ttu-id="380fb-174">[組織 **] タブ** を使用して、組織内でのユーザーの役割に関する詳細情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="380fb-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="380fb-175">**役職**</span><span class="sxs-lookup"><span data-stu-id="380fb-175">**Title**</span></span>
- <span data-ttu-id="380fb-176">**部署**</span><span class="sxs-lookup"><span data-stu-id="380fb-176">**Department**</span></span>
- <span data-ttu-id="380fb-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="380fb-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="380fb-178">EAC を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="380fb-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="380fb-179">EAC で、受信者の連絡先 **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="380fb-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="380fb-180">削除するメール ユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="380fb-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="380fb-181">PowerShell を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="380fb-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="380fb-182">スタンドアロンの EOP PowerShell を使用してメール ユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="380fb-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="380fb-183">スタンドアロンの EOP PowerShell ですべてのメール ユーザーの要約リストを返す場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="380fb-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="380fb-184">特定のメール ユーザーに関する詳細情報を表示するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換えて、次の \<MailUserIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="380fb-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="380fb-185">構文およびパラメーターの詳細については [、「Get-Recipient」](https://docs.microsoft.com/powershell/module/exchange/get-recipient) および [「Get-User」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-user)。</span><span class="sxs-lookup"><span data-stu-id="380fb-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="380fb-186">スタンドアロンの EOP PowerShell を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="380fb-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="380fb-187">スタンドアロンの EOP PowerShell でメール ユーザーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="380fb-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="380fb-188">**注**:</span><span class="sxs-lookup"><span data-stu-id="380fb-188">**Notes**:</span></span>

- <span data-ttu-id="380fb-189">Name _パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="380fb-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="380fb-190">_DisplayName_ パラメーターを使用しない場合 _、Name_ パラメーターの値が表示名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="380fb-191">_Alias_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ パラメーターの左側がエイリアスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="380fb-192">_ExternalEmailAddress_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ 値が外部電子メール アドレスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="380fb-193">この例では、次の設定でメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="380fb-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="380fb-194">名前は JeffreyZeng、表示名は Jeffrey Zeng です。</span><span class="sxs-lookup"><span data-stu-id="380fb-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="380fb-195">名は Jeffrey で、姓は Zeng です。</span><span class="sxs-lookup"><span data-stu-id="380fb-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="380fb-196">エイリアスは jeffreyz です。</span><span class="sxs-lookup"><span data-stu-id="380fb-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="380fb-197">外部の電子メール アドレスは jzeng@tailspintoys.com です。</span><span class="sxs-lookup"><span data-stu-id="380fb-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="380fb-198">アカウント名がjeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="380fb-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="380fb-199">パスワードは Pa$$word1 です。</span><span class="sxs-lookup"><span data-stu-id="380fb-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="380fb-200">構文およびパラメーターの詳細については [、「New-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="380fb-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="380fb-201">スタンドアロンの EOP PowerShell を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="380fb-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="380fb-202">スタンドアロンの EOP PowerShell で既存のメール ユーザーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="380fb-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="380fb-203">この例では、Pilar Pinilla の外部電子メール アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="380fb-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="380fb-204">この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="380fb-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="380fb-205">構文およびパラメーターの詳細については [、「Set-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="380fb-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="380fb-206">スタンドアロンの EOP PowerShell を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="380fb-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="380fb-207">スタンドアロンの EOP PowerShell でメール ユーザーを削除するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次の \<MailUserIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="380fb-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="380fb-208">この例では、Jeffrey Zeng のメール ユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="380fb-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="380fb-209">構文およびパラメーターの詳細については [、「Remove-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="380fb-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="380fb-210">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="380fb-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="380fb-211">スタンドアロン EOP でメール ユーザーが正常に作成、変更、または削除されたことを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="380fb-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="380fb-212">EAC で、受信者の連絡先 **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="380fb-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="380fb-213">メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。</span><span class="sxs-lookup"><span data-stu-id="380fb-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="380fb-214">メール ユーザーを選択し、[詳細] ウィンドウに情報を表示するか、[編集] アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-AddIcon.png) を表示します。</span><span class="sxs-lookup"><span data-stu-id="380fb-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="380fb-215">スタンドアロンの EOP PowerShell で、次のコマンドを実行して、メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。</span><span class="sxs-lookup"><span data-stu-id="380fb-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="380fb-216">メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して \<MailUserIdentity\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="380fb-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="380fb-217">ディレクトリ同期を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="380fb-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="380fb-218">スタンドアロン EOP では、オンプレミスの Active Directory を使用しているお客様がディレクトリ同期を利用できます。</span><span class="sxs-lookup"><span data-stu-id="380fb-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="380fb-219">これらのアカウントを Azure Active Directory (Azure AD) に同期し、アカウントのコピーがクラウドに保存されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="380fb-220">既存のユーザー アカウントを Azure Active Directory に同期する場合は、Exchange管理センター (EAC) の [受信者] ウィンドウまたはスタンドアロンの EOP PowerShell でそれらのユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="380fb-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="380fb-221">**注**:</span><span class="sxs-lookup"><span data-stu-id="380fb-221">**Notes**:</span></span>

- <span data-ttu-id="380fb-222">ディレクトリ同期を使用して受信者を管理する場合でも、Microsoft 365 管理センターでユーザーを追加および管理できますが、ユーザーはオンプレミスの Active Directory と同期されません。</span><span class="sxs-lookup"><span data-stu-id="380fb-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="380fb-223">これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="380fb-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="380fb-224">次の機能によるディレクトリ同期の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="380fb-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="380fb-225">**Outlook の差出** 人セーフ リストと受信拒否リスト : サービスに同期すると、これらのリストはサービスでのスパム フィルターよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="380fb-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="380fb-226">これにより、ユーザーは個々の送信者およびドメイン エントリを使用して、自分の差出人セーフ リストと受信拒否リストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="380fb-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="380fb-227">詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380fb-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="380fb-228">**ディレクトリ ベースのエッジ ブロック (DBEB)**: DBEB の詳細については、「ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する」を [参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="380fb-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="380fb-229">**エンド ユーザーの検疫への** アクセス : 検疫済みメッセージにアクセスするには、受信者がサービスに有効なユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="380fb-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="380fb-230">検疫の詳細については、「ユーザーとして検疫済み [メッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="380fb-230">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="380fb-231">メール フロー ルール (トランスポート ルールとも呼ばれる **)**: ディレクトリ同期を使用すると、既存の Active Directory ユーザーとグループが自動的にクラウドにアップロードされ、サービスに手動で追加することなく、特定のユーザーやグループを対象とするメール フロー ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="380fb-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="380fb-232">動的配布 [グループは、](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) ディレクトリ同期では同期できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="380fb-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="380fb-233">Azure Active Directory とのハイブリッド ID の説明に従って、必要なアクセス許可を取得し、 [ディレクトリ同期を準備します](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。</span><span class="sxs-lookup"><span data-stu-id="380fb-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="380fb-234">ディレクトリを Azure Active Directory Connect (AAD Connect) と同期する</span><span class="sxs-lookup"><span data-stu-id="380fb-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="380fb-235">Azure AD Connect 同期の説明に従って、ディレクトリ [同期をアクティブ化します。同期について理解し、カスタマイズします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="380fb-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="380fb-236">「Azure AD Connect の前提条件」の説明に従って、AAD Connect を実行するようにオンプレミス [のコンピューターをインストールしてADします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="380fb-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="380fb-237">Azure AD Connect に使用する[インストールの種類を選択します](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。</span><span class="sxs-lookup"><span data-stu-id="380fb-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="380fb-238">Express</span><span class="sxs-lookup"><span data-stu-id="380fb-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="380fb-239">Custom</span><span class="sxs-lookup"><span data-stu-id="380fb-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="380fb-240">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="380fb-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="380fb-p121">Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="380fb-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="380fb-244">同期を構成したら、AAD Connect が正しく同期されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="380fb-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="380fb-245">EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="380fb-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
