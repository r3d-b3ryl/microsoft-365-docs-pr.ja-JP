---
title: Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: ディレクトリ同期を使用してユーザーにMicrosoft 365準備する方法と、このメソッドを使用する長期的な利点について説明します。
ms.openlocfilehash: 7f701bf0a8b165323f7fd61b50b41fb5e18268a6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259561"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="7d462-103">Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)</span><span class="sxs-lookup"><span data-stu-id="7d462-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="7d462-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7d462-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7d462-105">組織のハイブリッド ID とディレクトリ同期の利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d462-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="7d462-106">組織内の管理プログラムの削減</span><span class="sxs-lookup"><span data-stu-id="7d462-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="7d462-107">必要に応じてシングル サインオン シナリオを有効にする</span><span class="sxs-lookup"><span data-stu-id="7d462-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="7d462-108">アカウントの変更を自動化するMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="7d462-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="7d462-109">ディレクトリ同期を使用する利点の詳細については、「ハイブリッド ID with [Azure Active Directory (Azure AD)」](/azure/active-directory/hybrid/whatis-hybrid-identity)および「ハイブリッド[ID」](plan-for-directory-synchronization.md)を参照Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7d462-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="7d462-110">ただし、ディレクトリ同期では、Active Directory ドメイン サービス (AD DS) が最小エラーで Microsoft 365 サブスクリプションの Azure AD テナントと同期するように計画と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="7d462-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="7d462-111">最適な結果を得るには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7d462-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="7d462-112">1. ディレクトリのクリーンアップ タスク</span><span class="sxs-lookup"><span data-stu-id="7d462-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="7d462-113">Ds を Azure ADテナントAD同期する前に、DS をクリーンアップするADがあります。</span><span class="sxs-lookup"><span data-stu-id="7d462-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d462-114">同期する前に DS クリーンアップAD実行しない場合、展開プロセスに大きな悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="7d462-115">ディレクトリ同期、エラーの特定、および再同期のサイクルを実行するには、数日または数週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="7d462-116">DS でADライセンスが割り当てられる各ユーザー アカウントについて、次のクリーンアップ タスクをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="7d462-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="7d462-117">proxyAddresses 属性で有効で一意の **電子メール アドレスを確認** します。</span><span class="sxs-lookup"><span data-stu-id="7d462-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="7d462-118">proxyAddresses 属性の重複 **する値を削除** します。</span><span class="sxs-lookup"><span data-stu-id="7d462-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="7d462-119">可能であれば、ユーザーのユーザー オブジェクトの **userPrincipalName** 属性の有効で一意の値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="7d462-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="7d462-120">最適な同期エクスペリエンスを得る場合は、DS UPN ADと AZURE の同期が一致ADしてください。</span><span class="sxs-lookup"><span data-stu-id="7d462-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="7d462-121">ユーザーに **userPrincipalName** 属性の値が設定されていない場合、ユーザーオブジェクトには **sAMAccountName** 属性の有効で一意の値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="7d462-122">**userPrincipalName 属性内の重複する値を削除** します。</span><span class="sxs-lookup"><span data-stu-id="7d462-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="7d462-123">グローバル アドレス一覧 (GAL) を最適に使用するには、DS ユーザー アカウントの次AD情報が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="7d462-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="7d462-124">givenName</span><span class="sxs-lookup"><span data-stu-id="7d462-124">givenName</span></span>
   - <span data-ttu-id="7d462-125">surname</span><span class="sxs-lookup"><span data-stu-id="7d462-125">surname</span></span>
   - <span data-ttu-id="7d462-126">displayName</span><span class="sxs-lookup"><span data-stu-id="7d462-126">displayName</span></span>
   - <span data-ttu-id="7d462-127">役職</span><span class="sxs-lookup"><span data-stu-id="7d462-127">Job Title</span></span>
   - <span data-ttu-id="7d462-128">部署</span><span class="sxs-lookup"><span data-stu-id="7d462-128">Department</span></span>
   - <span data-ttu-id="7d462-129">事業所</span><span class="sxs-lookup"><span data-stu-id="7d462-129">Office</span></span>
   - <span data-ttu-id="7d462-130">事業所電話番号</span><span class="sxs-lookup"><span data-stu-id="7d462-130">Office Phone</span></span>
   - <span data-ttu-id="7d462-131">携帯電話番号</span><span class="sxs-lookup"><span data-stu-id="7d462-131">Mobile Phone</span></span>
   - <span data-ttu-id="7d462-132">FAX 番号</span><span class="sxs-lookup"><span data-stu-id="7d462-132">Fax Number</span></span>
   - <span data-ttu-id="7d462-133">番地</span><span class="sxs-lookup"><span data-stu-id="7d462-133">Street Address</span></span>
   - <span data-ttu-id="7d462-134">都市</span><span class="sxs-lookup"><span data-stu-id="7d462-134">City</span></span>
   - <span data-ttu-id="7d462-135">都道府県</span><span class="sxs-lookup"><span data-stu-id="7d462-135">State or Province</span></span>
   - <span data-ttu-id="7d462-136">郵便番号</span><span class="sxs-lookup"><span data-stu-id="7d462-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="7d462-137">国または地域</span><span class="sxs-lookup"><span data-stu-id="7d462-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="7d462-138">2. ディレクトリ オブジェクトと属性の準備</span><span class="sxs-lookup"><span data-stu-id="7d462-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="7d462-139">DS とデバイス間のディレクトリ同期AD成功Microsoft 365 DS 属性を適切に準備ADする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="7d462-140">たとえば、特定の文字が特定の属性で使用され、特定の属性が特定の属性と同期Microsoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="7d462-141">予期しない文字を使用すると、ディレクトリ同期は失敗しませんが、警告が返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="7d462-142">無効な文字を指定すると、ディレクトリ同期が失敗します。</span><span class="sxs-lookup"><span data-stu-id="7d462-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="7d462-143">また、一部の DS ユーザーが 1 つ以上の重複AD場合、ディレクトリ同期は失敗します。</span><span class="sxs-lookup"><span data-stu-id="7d462-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="7d462-144">各ユーザーは、一意の属性を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="7d462-145">準備する必要がある属性を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7d462-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="7d462-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="7d462-146">**displayName**</span></span>

  - <span data-ttu-id="7d462-147">属性がユーザー オブジェクトに存在する場合、属性はユーザー オブジェクトと同期Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7d462-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="7d462-148">この属性がユーザー オブジェクトに存在する場合は、その属性の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="7d462-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="7d462-149">つまり、属性を空白にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d462-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="7d462-150">最大文字数: 256</span><span class="sxs-lookup"><span data-stu-id="7d462-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="7d462-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="7d462-151">**givenName**</span></span>

  - <span data-ttu-id="7d462-152">属性がユーザー オブジェクトに存在する場合、属性は Microsoft 365 と同期されますが、Microsoft 365を必要としたり使用したりしません。</span><span class="sxs-lookup"><span data-stu-id="7d462-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="7d462-153">最大文字数: 64</span><span class="sxs-lookup"><span data-stu-id="7d462-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="7d462-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="7d462-154">**mail**</span></span>

  - <span data-ttu-id="7d462-155">属性値はディレクトリ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d462-156">重複する値がある場合は、値を持つ最初のユーザーが同期されます。</span><span class="sxs-lookup"><span data-stu-id="7d462-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="7d462-157">後続のユーザーは、そのユーザーにMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="7d462-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="7d462-158">両方のユーザーが Microsoft 365に表示するには、AD DS の値を変更するか、両方の値を変更するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="7d462-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="7d462-159">**mailNickname** (Exchangeエイリアス)</span><span class="sxs-lookup"><span data-stu-id="7d462-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="7d462-160">属性値はピリオド (.) で始めできません。</span><span class="sxs-lookup"><span data-stu-id="7d462-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="7d462-161">属性値はディレクトリ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d462-162">同期名のアンダースコア ("_") は、この属性の元の値に無効な文字が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d462-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="7d462-163">この属性の詳細については、「alias 属性Exchange[参照してください](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="7d462-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="7d462-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="7d462-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="7d462-165">複数値属性</span><span class="sxs-lookup"><span data-stu-id="7d462-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="7d462-166">値あたりの最大文字数: 256</span><span class="sxs-lookup"><span data-stu-id="7d462-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="7d462-167">属性値にはスペースを含めずに指定してください。</span><span class="sxs-lookup"><span data-stu-id="7d462-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="7d462-168">属性値はディレクトリ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="7d462-169">無効な文字: \< \> ( ) ; , , [ ] "</span><span class="sxs-lookup"><span data-stu-id="7d462-169">Invalid characters: \< \> ( ) ; , [ ] "</span></span>

    <span data-ttu-id="7d462-170">無効な文字は、型の区切り文字と ":"に続く文字に適用され、SMTP:User@contso.com が許可されますが、SMTP:user:M@contoso.com されません。</span><span class="sxs-lookup"><span data-stu-id="7d462-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7d462-171">すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージングの標準に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="7d462-172">重複アドレスまたは不要なアドレスが存在する場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="7d462-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="7d462-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="7d462-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="7d462-174">最大文字数: 20</span><span class="sxs-lookup"><span data-stu-id="7d462-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="7d462-175">属性値はディレクトリ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="7d462-176">無効な文字: [ \ " | 、 / : \< \> + = ; ?</span><span class="sxs-lookup"><span data-stu-id="7d462-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="7d462-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="7d462-177">\* ']</span></span>
  - <span data-ttu-id="7d462-178">ユーザーが無効な **sAMAccountName** 属性を持ち、有効な **userPrincipalName** 属性を持つ場合、ユーザー アカウントはユーザー アカウントにMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="7d462-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="7d462-179">**sAMAccountName と** **userPrincipalName** の両方が無効な場合は、AD DS **userPrincipalName** 属性を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="7d462-180">**sn** (姓)</span><span class="sxs-lookup"><span data-stu-id="7d462-180">**sn** (surname)</span></span>

  - <span data-ttu-id="7d462-181">属性がユーザー オブジェクトに存在する場合、属性は Microsoft 365 と同期されますが、Microsoft 365を必要としたり使用したりしません。</span><span class="sxs-lookup"><span data-stu-id="7d462-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="7d462-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="7d462-182">**targetAddress**</span></span>

    <span data-ttu-id="7d462-183">ユーザーに対して設定された **targetAddress** 属性 (SMTP:tom@contoso.com など) が、MICROSOFT 365 GAL に表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="7d462-184">サード パーティ製のメッセージング移行シナリオでは、DS のMicrosoft 365スキーマ拡張機能がADされます。</span><span class="sxs-lookup"><span data-stu-id="7d462-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="7d462-185">またMicrosoft 365スキーマ拡張機能は、DS のディレクトリ同期ツールを使用してMicrosoft 365オブジェクトを管理するために、他の有用な属性ADします。</span><span class="sxs-lookup"><span data-stu-id="7d462-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="7d462-186">たとえば、非表示のメールボックスまたは配布グループを管理するための **msExchHideFromAddressLists** 属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d462-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="7d462-187">最大文字数: 256</span><span class="sxs-lookup"><span data-stu-id="7d462-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="7d462-188">属性値にはスペースを含めずに指定してください。</span><span class="sxs-lookup"><span data-stu-id="7d462-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="7d462-189">属性値はディレクトリ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="7d462-190">無効な文字: \ \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="7d462-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="7d462-191">すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージングの標準に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="7d462-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="7d462-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="7d462-193">**userPrincipalName** 属性は、インターネット スタイルのサインイン形式で、ユーザー名の後に at 記号 (@) とドメイン名 (たとえば、user@contoso.com) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="7d462-194">すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージングの標準に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="7d462-195">**userPrincipalName 属性** の最大文字数は 113 です。</span><span class="sxs-lookup"><span data-stu-id="7d462-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="7d462-196">次のように、アット記号 (@) の前と後に特定の文字数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d462-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="7d462-197">アット 記号の前にあるユーザー名の最大文字数 (@): 64</span><span class="sxs-lookup"><span data-stu-id="7d462-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="7d462-198">@記号 (@) に続くドメイン名の最大文字数: 48</span><span class="sxs-lookup"><span data-stu-id="7d462-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="7d462-199">無効な文字: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="7d462-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="7d462-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="7d462-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="7d462-201">使用できる文字: A ~ Z、a - z、0 ~ 9、' です。</span><span class="sxs-lookup"><span data-stu-id="7d462-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="7d462-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="7d462-202">- _ !</span></span> <span data-ttu-id="7d462-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="7d462-203"># ^ ~</span></span>
  - <span data-ttu-id="7d462-204">umlauts、アクセント、チルドなど、二等分記号を持つ文字は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="7d462-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="7d462-205">@ 文字は、各 **userPrincipalName 値で必要** です。</span><span class="sxs-lookup"><span data-stu-id="7d462-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="7d462-206">@ 文字は、各 **userPrincipalName** 値の最初の文字にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d462-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="7d462-207">ユーザー名は、ピリオド (.)、アンパサンド ( )、スペース、またはアット 記号 &amp; (@) で終了できません。</span><span class="sxs-lookup"><span data-stu-id="7d462-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="7d462-208">ユーザー名にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d462-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="7d462-209">Routable ドメインを使用する必要があります。たとえば、ローカル ドメインまたは内部ドメインは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7d462-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="7d462-210">Unicode はアンダースコア文字に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7d462-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="7d462-211">**userPrincipalName には** 、ディレクトリに重複する値を含めできません。</span><span class="sxs-lookup"><span data-stu-id="7d462-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="7d462-212">3. userPrincipalName 属性を準備する</span><span class="sxs-lookup"><span data-stu-id="7d462-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="7d462-213">Active Directory は、組織内のエンド ユーザーが **sAMAccountName** または **userPrincipalName** を使用してディレクトリにサインインするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7d462-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="7d462-214">同様に、エンド ユーザーは、自分のMicrosoft 365または学校アカウントのユーザー プリンシパル名 (UPN) を使用して、ユーザーにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="7d462-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="7d462-215">ディレクトリ同期は、DS 内の同Azure Active Directory UPN を使用して、新しいユーザーを作成ADします。</span><span class="sxs-lookup"><span data-stu-id="7d462-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="7d462-216">UPN は電子メール アドレスのように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="7d462-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="7d462-217">このMicrosoft 365 UPN は、電子メール アドレスの生成に使用される既定の属性です。</span><span class="sxs-lookup"><span data-stu-id="7d462-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="7d462-218">**userPrincipalName** (AD DS および Azure AD) と **proxyAddresses** のプライマリ 電子メール アドレスを異なる値に設定するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="7d462-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="7d462-219">異なる値に設定すると、管理者とエンド ユーザーが混乱する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="7d462-220">これらの属性を揃えて混乱を減らすのが最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="7d462-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="7d462-221">Active Directory フェデレーション サービス (AD FS) 2.0 でのシングル サインオンの要件を満たすには、Azure Active Directory の UPN と AD DS が一致し、有効なドメイン名前空間を使用していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="7d462-222">4. DS に代替 UPN サフィックスをADする</span><span class="sxs-lookup"><span data-stu-id="7d462-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="7d462-223">ユーザーの会社の資格情報をユーザー環境に関連付ける代替 UPN サフィックスを追加するMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="7d462-224">UPN サフィックスは、@ 文字の右側の UPN の一部です。</span><span class="sxs-lookup"><span data-stu-id="7d462-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="7d462-225">シングル サインオンに使用する UPN には文字、数字、ピリオド、ダッシュ、アンダースコアを含めることができますが、その他の種類の文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d462-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="7d462-226">代替 UPN サフィックスを Active Directory に追加する方法の詳細については、「ディレクトリ同期の準備 [」を参照してください]( https://go.microsoft.com/fwlink/p/?LinkId=525430)。</span><span class="sxs-lookup"><span data-stu-id="7d462-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="7d462-227">5. DS UPN AD UPN と一致Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="7d462-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="7d462-228">ディレクトリ同期を既に設定している場合、Microsoft 365 のユーザーの UPN が、AD DS で定義されているユーザーの AD DS UPN と一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="7d462-229">ドメインが確認される前にユーザーにライセンスを割り当てた場合、この状況が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7d462-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="7d462-230">これを修正するには[、PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396730)を使用して重複する UPN を修正してユーザーの UPN を更新し、Microsoft 365 UPN が会社のユーザー名とドメインと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="7d462-231">AD DS で UPN を更新し、Azure Active Directory ID と同期させる場合は、AD DS で変更を行う前に、Microsoft 365 でユーザーのライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d462-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="7d462-232">また、「 [ディレクトリ同期用に、.local](prepare-a-non-routable-domain-for-directory-synchronization.md)ドメインなど、ルートできないドメインを準備する方法」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d462-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d462-233">次の手順</span><span class="sxs-lookup"><span data-stu-id="7d462-233">Next steps</span></span>

<span data-ttu-id="7d462-234">上記の手順 1 ~ 5 を実行した場合は、「ディレクトリ同期の [セットアップ」を参照してください](set-up-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="7d462-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
