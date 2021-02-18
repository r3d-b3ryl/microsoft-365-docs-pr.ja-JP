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
description: ディレクトリ同期、EAC、PowerShell を使用してユーザーを管理する方法など、Exchange Online Protection (EOP) でメール ユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6a0dc1c0c343be77c6d6f713ee6b68a08a4fe5be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289915"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="5a542-103">スタンドアロン EOP でメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="5a542-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5a542-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="5a542-104">**Applies to**</span></span>
-  [<span data-ttu-id="5a542-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="5a542-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="5a542-106">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、メール ユーザーは基本的な種類のユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="5a542-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="5a542-107">メール ユーザーはスタンドアロン EOP 組織のアカウント資格情報を持ち、リソースにアクセスできます (アクセス許可が割り当てられている)。</span><span class="sxs-lookup"><span data-stu-id="5a542-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="5a542-108">メール ユーザーの電子メール アドレスは外部 (たとえば、オンプレミスのメール環境) です。</span><span class="sxs-lookup"><span data-stu-id="5a542-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="5a542-109">メール ユーザーを作成すると、対応するユーザー アカウントが Microsoft 365 管理センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="5a542-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5a542-110">Microsoft 365 管理センターでユーザー アカウントを作成する場合、そのアカウントを使用してメール ユーザーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a542-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="5a542-111">スタンドアロン EOP でメール ユーザーを作成および管理するには、この記事で後述する「ディレクトリ[](#use-directory-synchronization-to-manage-mail-users)同期を使用してメール ユーザーを管理する」セクションで説明するように、ディレクトリ同期を使用する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a542-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="5a542-112">ユーザー数が少ないスタンドアロン EOP 組織の場合は、この記事で説明するように、Exchange 管理センター (EAC) またはスタンドアロンの EOP PowerShell でメール ユーザーを追加および管理できます。</span><span class="sxs-lookup"><span data-stu-id="5a542-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5a542-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5a542-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5a542-114">Exchange 管理センター (EAC) を開く方法については、スタンドアロン EOP の [Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="5a542-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5a542-115">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a542-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5a542-116">EOP PowerShell でメール ユーザーを作成すると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a542-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="5a542-117">また、EOP PowerShell コマンドレットはバッチ処理方法を使用して、コマンドの結果が表示される数分前に伝達遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="5a542-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="5a542-118">この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a542-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="5a542-119">具体的には、既定で組織の管理 **(グローバル** 管理者) 役割グループと受信者管理役割グループに割り当てられる、メール受信者の作成 **(** 作成) 役割とメール受信者 **(変更**) 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a542-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="5a542-120">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="5a542-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="5a542-121">この記事の手順に適用されるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a542-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="5a542-122">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="5a542-122">Having problems?</span></span> <span data-ttu-id="5a542-123">Exchange のフォーラムで質問してください。</span><span class="sxs-lookup"><span data-stu-id="5a542-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="5a542-124">Exchange [Online Protection フォーラムにアクセス](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) します。</span><span class="sxs-lookup"><span data-stu-id="5a542-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="5a542-125">Exchange 管理センターを使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="5a542-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="5a542-126">EAC を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="5a542-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="5a542-127">EAC で、受信者の **連絡先に移動** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="5a542-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="5a542-128">[新 **しい新規]** ![ アイコンをクリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="5a542-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="5a542-129">開く **[新しいメール ユーザー** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5a542-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="5a542-130">an のマークが付いた設定 <sup>\*</sup> は必須です。</span><span class="sxs-lookup"><span data-stu-id="5a542-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="5a542-131">**名**</span><span class="sxs-lookup"><span data-stu-id="5a542-131">**First name**</span></span>

   - <span data-ttu-id="5a542-132">**イニシャル**: 人物の中間イニシャル。</span><span class="sxs-lookup"><span data-stu-id="5a542-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="5a542-133">**姓**</span><span class="sxs-lookup"><span data-stu-id="5a542-133">**Last name**</span></span>

   - <span data-ttu-id="5a542-134"><sup>\*</sup>**表示名**: 既定では、このボックスには [名]、[イニシャル]、および [氏名] ボックス **の値が** 表示されます。 </span><span class="sxs-lookup"><span data-stu-id="5a542-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="5a542-135">この値を受け入れるか、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5a542-135">You can accept this value or change it.</span></span> <span data-ttu-id="5a542-136">値は一意で、最大長は 64 文字です。</span><span class="sxs-lookup"><span data-stu-id="5a542-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="5a542-137"><sup>\*</sup>**エイリアス**: ユーザーに対して最大 64 文字を使用して一意のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a542-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="5a542-138">**外部電子メール アドレス**: ユーザーの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a542-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="5a542-139">ドメインはクラウドベースの組織の外部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a542-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="5a542-140"><sup>\*</sup>**ユーザー ID**: ユーザーがサービスにサインインするために使用するアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a542-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="5a542-141">ユーザー ID は、at (@) 記号 (@) の左側のユーザー名と右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="5a542-142"><sup>\*</sup>**新しいパスワード** と <sup>\*</sup> **パスワードの確認**: アカウントパスワードを入力して再入力します。</span><span class="sxs-lookup"><span data-stu-id="5a542-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="5a542-143">パスワードが組織のパスワードの長さ、複雑さ、履歴の要件に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a542-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="5a542-144">完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a542-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="5a542-145">EAC を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="5a542-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="5a542-146">EAC で、受信者の連絡先 **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="5a542-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="5a542-147">変更するメール ユーザーを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="5a542-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="5a542-148">表示されたメール ユーザーのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="5a542-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="5a542-149">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a542-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="5a542-150">全般</span><span class="sxs-lookup"><span data-stu-id="5a542-150">General</span></span>

<span data-ttu-id="5a542-151">[全般 **] タブ** を使用して、メール ユーザーに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="5a542-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="5a542-152">**名**</span><span class="sxs-lookup"><span data-stu-id="5a542-152">**First name**</span></span>

- <span data-ttu-id="5a542-153">**頭文字**</span><span class="sxs-lookup"><span data-stu-id="5a542-153">**Initials**</span></span>

- <span data-ttu-id="5a542-154">**姓**</span><span class="sxs-lookup"><span data-stu-id="5a542-154">**Last name**</span></span>

- <span data-ttu-id="5a542-155">**表示名**: この名前は、組織のアドレス帳、電子メールの [To:] 行と [From:] 行、および EAC の連絡先の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="5a542-156">この名前は、表示名の前または後に空のスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a542-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="5a542-157">**ユーザー ID**: Microsoft 365 のユーザーのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="5a542-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="5a542-158">この値はここで変更できます。</span><span class="sxs-lookup"><span data-stu-id="5a542-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="5a542-159">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="5a542-159">Contact information</span></span>

<span data-ttu-id="5a542-160">[連絡先情報 **] タブを** 使用して、ユーザーの連絡先情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="5a542-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="5a542-161">このページの情報がアドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="5a542-162">**Street**</span><span class="sxs-lookup"><span data-stu-id="5a542-162">**Street**</span></span>
- <span data-ttu-id="5a542-163">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="5a542-163">**City**</span></span>
- <span data-ttu-id="5a542-164">**都道府県**</span><span class="sxs-lookup"><span data-stu-id="5a542-164">**State/Province**</span></span>
- <span data-ttu-id="5a542-165">**郵便番号**</span><span class="sxs-lookup"><span data-stu-id="5a542-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="5a542-166">**国/地域設定**</span><span class="sxs-lookup"><span data-stu-id="5a542-166">**Country/Region**</span></span>
- <span data-ttu-id="5a542-167">**勤務先の電話番号**</span><span class="sxs-lookup"><span data-stu-id="5a542-167">**Work phone**</span></span>
- <span data-ttu-id="5a542-168">**携帯電話**</span><span class="sxs-lookup"><span data-stu-id="5a542-168">**Mobile phone**</span></span>
- <span data-ttu-id="5a542-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="5a542-169">**Fax**</span></span>
- <span data-ttu-id="5a542-170">**[その他のオプション]**</span><span class="sxs-lookup"><span data-stu-id="5a542-170">**More options**</span></span>

  - <span data-ttu-id="5a542-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="5a542-171">**Office**</span></span>
  - <span data-ttu-id="5a542-172">**自宅電話**</span><span class="sxs-lookup"><span data-stu-id="5a542-172">**Home phone**</span></span>
  - <span data-ttu-id="5a542-173">**Web ページ**</span><span class="sxs-lookup"><span data-stu-id="5a542-173">**Web page**</span></span>
  - <span data-ttu-id="5a542-174">**注**</span><span class="sxs-lookup"><span data-stu-id="5a542-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="5a542-175">組織</span><span class="sxs-lookup"><span data-stu-id="5a542-175">Organization</span></span>

<span data-ttu-id="5a542-176">[組織 **] タブ** を使用して、組織内でのユーザーの役割に関する詳細情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="5a542-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="5a542-177">**役職**</span><span class="sxs-lookup"><span data-stu-id="5a542-177">**Title**</span></span>
- <span data-ttu-id="5a542-178">**部署**</span><span class="sxs-lookup"><span data-stu-id="5a542-178">**Department**</span></span>
- <span data-ttu-id="5a542-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="5a542-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="5a542-180">EAC を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="5a542-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="5a542-181">EAC で、受信者の連絡先 **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="5a542-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="5a542-182">削除するメール ユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="5a542-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="5a542-183">PowerShell を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="5a542-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="5a542-184">スタンドアロンの EOP PowerShell を使用してメール ユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="5a542-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="5a542-185">スタンドアロンの EOP PowerShell ですべてのメール ユーザーの要約リストを返す場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a542-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="5a542-186">特定のメール ユーザーに関する詳細情報を表示するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換えて、次の \<MailUserIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a542-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="5a542-187">構文およびパラメーターの詳細については [、「Get-Recipient」](https://docs.microsoft.com/powershell/module/exchange/get-recipient) および [「Get-User」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-user)。</span><span class="sxs-lookup"><span data-stu-id="5a542-187">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="5a542-188">スタンドアロンの EOP PowerShell を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="5a542-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="5a542-189">スタンドアロンの EOP PowerShell でメール ユーザーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a542-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="5a542-190">**注**:</span><span class="sxs-lookup"><span data-stu-id="5a542-190">**Notes**:</span></span>

- <span data-ttu-id="5a542-191">Name _パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a542-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="5a542-192">_DisplayName_ パラメーターを使用しない場合 _、Name_ パラメーターの値が表示名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="5a542-193">_Alias_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ パラメーターの左側がエイリアスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="5a542-194">_ExternalEmailAddress_ パラメーターを使用しない場合は _、MicrosoftOnlineServicesID_ 値が外部電子メール アドレスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="5a542-195">この例では、次の設定でメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a542-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="5a542-196">名前は JeffreyZeng、表示名は Jeffrey Zeng です。</span><span class="sxs-lookup"><span data-stu-id="5a542-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="5a542-197">名は Jeffrey で、姓は Zeng です。</span><span class="sxs-lookup"><span data-stu-id="5a542-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="5a542-198">エイリアスは jeffreyz です。</span><span class="sxs-lookup"><span data-stu-id="5a542-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="5a542-199">外部の電子メール アドレスは jzeng@tailspintoys.com です。</span><span class="sxs-lookup"><span data-stu-id="5a542-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="5a542-200">アカウント名がjeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="5a542-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="5a542-201">パスワードは Pa$$word1 です。</span><span class="sxs-lookup"><span data-stu-id="5a542-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="5a542-202">構文およびパラメーターの詳細については [、「New-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="5a542-202">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="5a542-203">スタンドアロンの EOP PowerShell を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="5a542-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="5a542-204">スタンドアロンの EOP PowerShell で既存のメール ユーザーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a542-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="5a542-205">この例では、Pilar Pinilla の外部電子メール アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a542-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="5a542-206">この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="5a542-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="5a542-207">構文およびパラメーターの詳細については [、「Set-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="5a542-207">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="5a542-208">スタンドアロンの EOP PowerShell を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="5a542-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="5a542-209">スタンドアロンの EOP PowerShell でメール ユーザーを削除するには、メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次の \<MailUserIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a542-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="5a542-210">この例では、Jeffrey Zeng のメール ユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5a542-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="5a542-211">構文およびパラメーターの詳細については [、「Remove-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="5a542-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5a542-212">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="5a542-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="5a542-213">スタンドアロン EOP でメール ユーザーが正常に作成、変更、または削除されたことを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a542-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="5a542-214">EAC で、受信者の連絡先 **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="5a542-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="5a542-215">メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。</span><span class="sxs-lookup"><span data-stu-id="5a542-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="5a542-216">メール ユーザーを選択し、[詳細] ウィンドウに情報を表示するか、[編集] アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-AddIcon.png) を表示します。</span><span class="sxs-lookup"><span data-stu-id="5a542-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="5a542-217">スタンドアロンの EOP PowerShell で、次のコマンドを実行して、メール ユーザーが一覧に表示されている (または一覧に表示されていない) か確認します。</span><span class="sxs-lookup"><span data-stu-id="5a542-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="5a542-218">メール ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して \<MailUserIdentity\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a542-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="5a542-219">ディレクトリ同期を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="5a542-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="5a542-220">スタンドアロン EOP では、オンプレミスの Active Directory を使用しているお客様がディレクトリ同期を利用できます。</span><span class="sxs-lookup"><span data-stu-id="5a542-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="5a542-221">これらのアカウントを Azure Active Directory (Azure AD) に同期し、アカウントのコピーがクラウドに保存されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="5a542-222">既存のユーザー アカウントを Azure Active Directory に同期する場合は、Exchange管理センター (EAC) の [受信者] ウィンドウまたはスタンドアロンの EOP PowerShell でそれらのユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5a542-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="5a542-223">**注**:</span><span class="sxs-lookup"><span data-stu-id="5a542-223">**Notes**:</span></span>

- <span data-ttu-id="5a542-224">ディレクトリ同期を使用して受信者を管理する場合でも、Microsoft 365 管理センターでユーザーを追加および管理できますが、ユーザーはオンプレミスの Active Directory と同期されません。</span><span class="sxs-lookup"><span data-stu-id="5a542-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="5a542-225">これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="5a542-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="5a542-226">次の機能によるディレクトリ同期の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a542-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="5a542-227">**Outlook の差出** 人セーフ リストと受信拒否リスト : サービスに同期すると、これらのリストはサービスでのスパム フィルターよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5a542-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="5a542-228">これにより、ユーザーは個々の送信者およびドメイン エントリを使用して、自分の差出人セーフ リストと受信拒否リストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="5a542-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="5a542-229">詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a542-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="5a542-230">**ディレクトリ ベースのエッジ ブロック (DBEB)**: DBEB の詳細については、「ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する」を [参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="5a542-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="5a542-231">**エンド ユーザーの検疫への** アクセス : 検疫済みメッセージにアクセスするには、受信者がサービスに有効なユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a542-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="5a542-232">検疫の詳細については、「ユーザーとして検疫済み [メッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="5a542-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="5a542-233">メール フロー ルール (トランスポート ルールとも呼ばれる **)**: ディレクトリ同期を使用すると、既存の Active Directory ユーザーとグループが自動的にクラウドにアップロードされ、サービスに手動で追加することなく、特定のユーザーやグループを対象とするメール フロー ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a542-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="5a542-234">動的配布 [グループは、](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) ディレクトリ同期では同期できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a542-234">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="5a542-235">Azure Active Directory とのハイブリッド ID の説明に従って、必要なアクセス許可を取得し、 [ディレクトリ同期を準備します](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。</span><span class="sxs-lookup"><span data-stu-id="5a542-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="5a542-236">ディレクトリを Azure Active Directory Connect (AAD Connect) と同期する</span><span class="sxs-lookup"><span data-stu-id="5a542-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="5a542-237">Azure AD Connect 同期の説明に従って、ディレクトリ [同期をアクティブ化します。同期について理解し、カスタマイズします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="5a542-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="5a542-238">「Azure AD Connect の前提条件」の説明に従って、AAD Connect を実行するようにオンプレミス [のコンピューターをインストールしてADします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="5a542-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="5a542-239">Azure AD Connect に使用する[インストールの種類を選択します](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。</span><span class="sxs-lookup"><span data-stu-id="5a542-239">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="5a542-240">Express</span><span class="sxs-lookup"><span data-stu-id="5a542-240">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="5a542-241">Custom</span><span class="sxs-lookup"><span data-stu-id="5a542-241">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="5a542-242">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="5a542-242">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="5a542-p121">Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a542-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="5a542-246">同期を構成したら、AAD Connect が正しく同期されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a542-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="5a542-247">EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a542-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
