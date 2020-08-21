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
description: ユーザーの管理でのディレクトリ同期、EAC、PowerShell の使用など、Exchange Online Protection (EOP) でメール ユーザーを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827077"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="eb20a-103">スタンドアロン EOP でメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="eb20a-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="eb20a-104">Exchange Online メールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織の場合、メール ユーザーは基本タイプのユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="eb20a-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="eb20a-105">メール ユーザーは、スタンドアロン EOP 組織のアカウント資格情報を持っており、リソースにアクセスできます (アクセス許可の割り当てが付与されている)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="eb20a-106">メール ユーザーの電子メール アドレスが外部 (社内の電子メール環境など) である。</span><span class="sxs-lookup"><span data-stu-id="eb20a-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="eb20a-107">メール ユーザーを作成する場合、対応するユーザー アカウントは Microsoft 365 管理センターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="eb20a-108">Microsoft 365 管理センターでユーザー アカウントを作成する際、そのアカウントを使用してメール ユーザーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="eb20a-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="eb20a-109">スタンドアロン EOP でメール ユーザーを作成および管理する方法として、このトピックの後半のセクションで説明している「ディレクトリ同期を使用する [」で説明](#use-directory-synchronization-to-manage-mail-users) されているとおりに、ディレクトリ同期を使用する方法が推奨されています。</span><span class="sxs-lookup"><span data-stu-id="eb20a-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="eb20a-110">ユーザー数がわずかで組織の場合は、このトピックで説明されている方法で、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell でメール ユーザーを追加して管理できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eb20a-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="eb20a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eb20a-112">Exchange 管理センター (EAC) を開くには、スタンドアロン [EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="eb20a-113">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb20a-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="eb20a-114">EOP PowerShell でメール ユーザーを作成する場合、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb20a-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="eb20a-115">また、EOP PowerShell コマンドレットはバッチ処理方法を使用します。この方法では、コマンドの結果が表示されるまで数分の送信遅延がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="eb20a-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="eb20a-116">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb20a-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="eb20a-117">具体的には、メール受信者の作成 (作成) 役割とメール受信者 (変更) 役割が必要です。既定で OrganizationManagement (グローバル管理者) 役割と RecipientManagement 役割グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="eb20a-118">詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="eb20a-119">このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="eb20a-120">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="eb20a-120">Having problems?</span></span> <span data-ttu-id="eb20a-121">Exchange のフォーラムで質問してください。</span><span class="sxs-lookup"><span data-stu-id="eb20a-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="eb20a-122">[Exchange Online Protection フォーラム](https://go.microsoft.com/fwlink/p/?linkId=285351)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="eb20a-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="eb20a-123">Exchange 管理センターを使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="eb20a-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="eb20a-124">EAC を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="eb20a-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="eb20a-125">EAC で、受信者の連絡先に **移動** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="eb20a-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="eb20a-126">新規作成 **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="eb20a-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="eb20a-127">表示される **[新しいメール ユーザー** ] ページで、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="eb20a-128">必須のマークが付いいい <sup>\*</sup> いの設定は、必須です。</span><span class="sxs-lookup"><span data-stu-id="eb20a-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="eb20a-129">**名**</span><span class="sxs-lookup"><span data-stu-id="eb20a-129">**First name**</span></span>

   - <span data-ttu-id="eb20a-130">**イニシャ**ル : 人物のミドル ネームのイニシャル。</span><span class="sxs-lookup"><span data-stu-id="eb20a-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="eb20a-131">**姓**</span><span class="sxs-lookup"><span data-stu-id="eb20a-131">**Last name**</span></span>

   - <span data-ttu-id="eb20a-132"><sup>\*</sup>**表示名**: 既定では、このボックスには [名]、[イニシャル **]、[姓]\*\*\*\*ボックス**の値**が表示**されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="eb20a-133">この値をその値の入れ、変更を行う。</span><span class="sxs-lookup"><span data-stu-id="eb20a-133">You can accept this value or change it.</span></span> <span data-ttu-id="eb20a-134">値は一意で、最大で 64 文字です。</span><span class="sxs-lookup"><span data-stu-id="eb20a-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="eb20a-135"><sup>\*</sup>**エイリア**ス: ユーザーに対しては、最大 64 文字で一意のエイリアスを入力します</span><span class="sxs-lookup"><span data-stu-id="eb20a-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="eb20a-136">**[外部の電子メール**アドレス]: ユーザーの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="eb20a-137">ドメインはクラウドベース組織の外部ドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb20a-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="eb20a-138"><sup>\*</sup>**[ユーザー ID]:** ユーザーがサービスにサインインするために使用するアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="eb20a-139">ユーザー ID は、アットマーク (@) の左側のユーザー名と右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="eb20a-140"><sup>\*</sup>**[New password]** (新 <sup>\*</sup> **しいパスワード) とパスワード**の確認: アカウントのパスワードを入力し、再入力します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="eb20a-141">パスワードが組織のパスワードの長さ、複雑さ、および履歴に関する要件に準拠していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb20a-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="eb20a-142">完了したら、 **[保存]** をクリックしてメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="eb20a-143">EAC を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="eb20a-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="eb20a-144">EAC で、[受信者の連絡先] **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="eb20a-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="eb20a-145">変更するメール ユーザーを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="eb20a-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="eb20a-146">表示されるメール ユーザーのプロパティ ページで、次のいずれかのタブをクリックして、プロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="eb20a-147">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb20a-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="eb20a-148">全般</span><span class="sxs-lookup"><span data-stu-id="eb20a-148">General</span></span>

<span data-ttu-id="eb20a-149">[全般 **]** タブを使用して、メール ユーザーに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="eb20a-150">**名**</span><span class="sxs-lookup"><span data-stu-id="eb20a-150">**First name**</span></span>

- <span data-ttu-id="eb20a-151">**頭文字**</span><span class="sxs-lookup"><span data-stu-id="eb20a-151">**Initials**</span></span>

- <span data-ttu-id="eb20a-152">**姓**</span><span class="sxs-lookup"><span data-stu-id="eb20a-152">**Last name**</span></span>

- <span data-ttu-id="eb20a-153">**表示名**: この名前は組織のアドレス帳、電子メールの "送信先行" 行と "From: /外部アドレス" 行、および EAC の連絡先の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="eb20a-154">この名前は、表示名の前または後に空のスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb20a-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="eb20a-155">**[ユーザー ID]:** Microsoft 365 でのユーザーのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="eb20a-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="eb20a-156">ここで、この値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="eb20a-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="eb20a-157">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="eb20a-157">Contact information</span></span>

<span data-ttu-id="eb20a-158">[連絡先 **情報] タブ** を使用して、ユーザーの連絡先情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="eb20a-159">このページの情報がアドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="eb20a-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="eb20a-160">**Street**</span></span>
- <span data-ttu-id="eb20a-161">**市区町村**</span><span class="sxs-lookup"><span data-stu-id="eb20a-161">**City**</span></span>
- <span data-ttu-id="eb20a-162">**都道府県**</span><span class="sxs-lookup"><span data-stu-id="eb20a-162">**State/Province**</span></span>
- <span data-ttu-id="eb20a-163">**郵便番号**</span><span class="sxs-lookup"><span data-stu-id="eb20a-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="eb20a-164">**国/地域設定**</span><span class="sxs-lookup"><span data-stu-id="eb20a-164">**Country/Region**</span></span>
- <span data-ttu-id="eb20a-165">**勤務先の電話番号**</span><span class="sxs-lookup"><span data-stu-id="eb20a-165">**Work phone**</span></span>
- <span data-ttu-id="eb20a-166">**携帯電話**</span><span class="sxs-lookup"><span data-stu-id="eb20a-166">**Mobile phone**</span></span>
- <span data-ttu-id="eb20a-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="eb20a-167">**Fax**</span></span>
- <span data-ttu-id="eb20a-168">**[その他のオプション]**</span><span class="sxs-lookup"><span data-stu-id="eb20a-168">**More options**</span></span>

  - <span data-ttu-id="eb20a-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="eb20a-169">**Office**</span></span>
  - <span data-ttu-id="eb20a-170">**自宅電話**</span><span class="sxs-lookup"><span data-stu-id="eb20a-170">**Home phone**</span></span>
  - <span data-ttu-id="eb20a-171">**Web ページ**</span><span class="sxs-lookup"><span data-stu-id="eb20a-171">**Web page**</span></span>
  - <span data-ttu-id="eb20a-172">**注**</span><span class="sxs-lookup"><span data-stu-id="eb20a-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="eb20a-173">組織</span><span class="sxs-lookup"><span data-stu-id="eb20a-173">Organization</span></span>

<span data-ttu-id="eb20a-174">[組織 **]** タブを使用すると、組織内のユーザーの役割に関する詳細情報を記録できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="eb20a-175">**役職**</span><span class="sxs-lookup"><span data-stu-id="eb20a-175">**Title**</span></span>
- <span data-ttu-id="eb20a-176">**部署**</span><span class="sxs-lookup"><span data-stu-id="eb20a-176">**Department**</span></span>
- <span data-ttu-id="eb20a-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="eb20a-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="eb20a-178">EAC を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="eb20a-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="eb20a-179">EAC で、[受信者の連絡先] **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="eb20a-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="eb20a-180">削除するメール ユーザーを選び、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="eb20a-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="eb20a-181">PowerShell を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="eb20a-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="eb20a-182">スタンドアロン EOP PowerShell を使用してメール ユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="eb20a-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="eb20a-183">スタンドアロン EOP PowerShell 内のすべてのメール ユーザーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="eb20a-184">特定のメール ユーザーに関する詳細情報を表示するには、メール \<MailUserIdentity\> ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="eb20a-185">構文およびパラメーターの詳細については[、「Get-Recipient」と「Get-User」](https://docs.microsoft.com/powershell/module/exchange/get-recipient)[を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-user)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="eb20a-186">スタンドアロン EOP PowerShell を使用してメール ユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="eb20a-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="eb20a-187">スタンドアロン EOP PowerShell でメール ユーザーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="eb20a-188">**注**:</span><span class="sxs-lookup"><span data-stu-id="eb20a-188">**Notes**:</span></span>

- <span data-ttu-id="eb20a-189">_Name パラメーターは_必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb20a-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="eb20a-190">DisplayName パラメーターを使用し_なけら__、Name パラメーターの値_が表示名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="eb20a-191">_Alias_パラメーターを使用しない場合は _、MicrosoftOnlineServicesID パラメーターの左側_がエイリアスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="eb20a-192">ExternalEmailAddress パラメーターを使用 _しない場合は_ 、 _外部電子メール アドレスに MicrosoftOnlineServicesID_ の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="eb20a-193">この例では、次の設定でメール ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="eb20a-194">名前は JeffreyZeng で、表示名は Jeffrey Zeng です。</span><span class="sxs-lookup"><span data-stu-id="eb20a-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="eb20a-195">名は Jeffrey で、姓は Zeng です。</span><span class="sxs-lookup"><span data-stu-id="eb20a-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="eb20a-196">エイリアスは jeffreyz です。</span><span class="sxs-lookup"><span data-stu-id="eb20a-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="eb20a-197">外部の電子メール アドレスは jzeng@tailspintoys.com です。</span><span class="sxs-lookup"><span data-stu-id="eb20a-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="eb20a-198">アカウント名は次jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="eb20a-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="eb20a-199">パスワードは Pa$$word1 です。</span><span class="sxs-lookup"><span data-stu-id="eb20a-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="eb20a-200">構文およびパラメーターの詳細については [、「New-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="eb20a-201">スタンドアロン EOP PowerShell を使用してメール ユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="eb20a-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="eb20a-202">スタンドアロン EOP PowerShell で既存のメール ユーザーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="eb20a-203">この例では、Pilar Pinilla の外部電子メール アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="eb20a-204">この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="eb20a-205">構文およびパラメーターの詳細については [、「Set-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="eb20a-206">スタンドアロン EOP PowerShell を使用してメール ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="eb20a-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="eb20a-207">スタンドアロン EOP PowerShell 内のメール ユーザーを削除するには、メール \<MailUserIdentity\> ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="eb20a-208">この例では、Jeffrey Zeng のメール ユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="eb20a-209">構文およびパラメーターの詳細については [、「Remove-EOPMailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="eb20a-210">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="eb20a-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="eb20a-211">スタンドアロン EOP でメール ユーザーの作成、変更、または削除が正常に行化されたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="eb20a-212">EAC で、[受信者の連絡先] **に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="eb20a-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="eb20a-213">メール ユーザーが一覧に表示されている (または一覧に表示されていない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="eb20a-214">メール ユーザーを選択して詳細ウィンドウに情報を表示するか、設定を \*\*表示するには [\*\* ![ 編集] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb20a-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="eb20a-215">スタンドアロン EOP PowerShell で、次のコマンドを実行して、メール ユーザーが一覧に表示されている (または一覧にない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="eb20a-216">メール \<MailUserIdentity\> ユーザーの名前、エイリアス、またはアカウント名に置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="eb20a-217">ディレクトリ同期を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="eb20a-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="eb20a-218">スタンドアロン EOP では、オンプレミスの Active Directory を使用しているお客様はディレクトリ同期を利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="eb20a-219">アカウントのコピーがクラウドに格納される Azure Active Directory (Azure AD) にこれらのアカウントを同期できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="eb20a-220">既存のユーザー アカウントを Azure Active Directory に同期するときには、Exchange**Recipients**管理センター (EAC) の受信者ウィンドウまたはスタンドアロン EOP PowerShell で該当するユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="eb20a-221">**注**:</span><span class="sxs-lookup"><span data-stu-id="eb20a-221">**Notes**:</span></span>

- <span data-ttu-id="eb20a-222">ディレクトリ同期を使って受信者を管理する場合でも、Microsoft 365 管理センター でユーザーの追加と管理は可能ですが、これらのユーザーは社内 Active Directory を使う同期の設定が行なされません。</span><span class="sxs-lookup"><span data-stu-id="eb20a-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="eb20a-223">これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="eb20a-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="eb20a-224">次の機能によるディレクトリ同期の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eb20a-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="eb20a-225">**Outlook の差出人セーフ リスト**と受信拒否リスト: サービスに同期すると、これらのリストはサービスのスパム フィルターより優先されます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="eb20a-226">これにより、ユーザーは個々の差出人とドメイン エントリを使って、独自の信頼できる差出人のリストと受信拒否リストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="eb20a-227">詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb20a-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="eb20a-228">**ディレクトリ ベースのエッジ ブロック (DBEB):** DBEB の詳細については、「ディレクトリ [ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="eb20a-229">**検疫へのエンド ユーザー アクセス**: 検疫済みメッセージにアクセスするには、受信者はサービスに有効なユーザー ID とパスワードを持っていなけれなけれなけれないでください。</span><span class="sxs-lookup"><span data-stu-id="eb20a-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="eb20a-230">検疫の詳細については、「ユーザーが検 [疫済みメッセージを検索して解放する」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="eb20a-231">**メール フロー ルール (トランスポート ルールとも呼ばれる):** ディレクトリ同期を使用すると、既存の Active Directory のユーザーとグループが自動的にクラウドにアップロードされ、サービスに手動で追加しなくても特定のユーザーやグループを対象とするメール フロー ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="eb20a-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="eb20a-232">動的配布 [グループをディレクトリ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 同期によって同期することはできません。</span><span class="sxs-lookup"><span data-stu-id="eb20a-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="eb20a-233">Azure Active Directory とのハイブリッド ID についての説明に説明されているように、必要なアクセス [許可を取得し、ディレクトリ同期を準備します](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="eb20a-234">Azure Active Directory Connect (AAD Connect) とディレクトリを同期する</span><span class="sxs-lookup"><span data-stu-id="eb20a-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="eb20a-235">Azure の同期の詳細に説明されている [ようにAD、同期の理解とカスタマイズ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="eb20a-236">Azure AD Connect の前提条件に関する説明に基づいて AAD Connect を実行するオンプレミス [のコンピューターをインストールしてADします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="eb20a-237">[Azure の Connect で使用するインストールの種類ADします](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。</span><span class="sxs-lookup"><span data-stu-id="eb20a-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="eb20a-238">Express</span><span class="sxs-lookup"><span data-stu-id="eb20a-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="eb20a-239">Custom</span><span class="sxs-lookup"><span data-stu-id="eb20a-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="eb20a-240">パススルー認証</span><span class="sxs-lookup"><span data-stu-id="eb20a-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="eb20a-p121">Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb20a-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="eb20a-244">同期を構成した後は、AAD Connect が正しく同期することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb20a-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="eb20a-245">EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb20a-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
