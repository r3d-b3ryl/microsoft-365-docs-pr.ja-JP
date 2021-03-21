---
title: 検疫タグ
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 管理者は、検疫タグを使用して、検疫済みメッセージに対してユーザーが実行できる操作を制御する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8024894cdb4a4718422c250eff87fa6da5443a84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922414"
---
# <a name="quarantine-tags"></a><span data-ttu-id="0dec2-103">検疫タグ</span><span class="sxs-lookup"><span data-stu-id="0dec2-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="0dec2-104">この記事で説明する機能は、現在プレビュー中であり、すべてのユーザーが利用できる機能ではなく、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0dec2-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="0dec2-105">Exchange Online Protection (EOP) の検疫タグを使用すると、管理者は、メッセージが検疫に到着した方法に基づいて、検疫済みメッセージに対してユーザーが実行できる操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="0dec2-106">EOP は、従来、検疫およびエンド ユーザーのスパム通知のメッセージに[](find-and-release-quarantined-messages-as-a-user.md)対して、特定のレベルの対話機能を許可または[防止しています](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="0dec2-107">たとえば、エンド ユーザーはスパム対策フィルターによって検疫されたメッセージをスパムまたはバルクとして表示および解放できますが、高信頼フィッシングとして検疫されたメッセージを表示または解放したりはしません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="0dec2-108">サポート [される保護機能](#step-2-assign-a-quarantine-tag-to-supported-features)の場合、検疫タグは、エンドユーザーのスパム通知メッセージと検疫中の検疫済みメッセージ (ユーザーが受信者であるメッセージ) でユーザーが実行できる操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="0dec2-109">既定の検疫タグは自動的に割り当て、検疫済みメッセージにエンド ユーザーの履歴機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="0dec2-110">または、カスタム検疫タグを作成して割り当て、エンド ユーザーが検疫済みメッセージに対して特定のアクションを実行する許可または防止を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="0dec2-111">個々のアクセス許可は、次の事前設定されたアクセス許可グループに組み合わされます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="0dec2-112">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="0dec2-112">No access</span></span>
- <span data-ttu-id="0dec2-113">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-113">Limited access</span></span>
- <span data-ttu-id="0dec2-114">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-114">Full access</span></span>

<span data-ttu-id="0dec2-115">使用可能な個々のアクセス許可と、事前設定されたアクセス許可グループに含まれているか含まれていないかについて、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="0dec2-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="0dec2-116">Permission</span></span>|<span data-ttu-id="0dec2-117">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="0dec2-117">No access</span></span>|<span data-ttu-id="0dec2-118">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-118">Limited access</span></span>|<span data-ttu-id="0dec2-119">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="0dec2-120">**送信者を許可** する (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="0dec2-122">**送信者のブロック** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="0dec2-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-125">**Delete** (_PermissionToDelete_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="0dec2-128">**プレビュー** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-128">**Preview** (_PermissionToPreview_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="0dec2-131">**受信者に検疫からのメッセージの解放を許可** する (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="0dec2-133">**受信者がメッセージを検疫から** 解放する要求を許可する (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![チェック マーク](../../media/checkmark.png)||
|

<span data-ttu-id="0dec2-135">事前設定されたアクセス許可グループの既定のアクセス許可が気に入らない場合は、カスタム検疫タグを作成または変更するときにカスタムアクセス許可を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="0dec2-136">各アクセス許可の動作の詳細については、この記事の後半の「 [検疫タグのアクセス許可の詳細](#quarantine-tag-permission-details) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="0dec2-137">検疫タグは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online メールボックスを使用する Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない EOP 組織のスタンドアロン EOP PowerShell) で作成および割り当てる。</span><span class="sxs-lookup"><span data-stu-id="0dec2-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0dec2-138">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0dec2-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0dec2-139"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0dec2-140">[検疫タグ] ページに直接 **移動するには** 、 を開きます <https://protection.office.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="0dec2-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="0dec2-141">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0dec2-142">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0dec2-143">検疫タグを表示、作成、変更、または削除するには、セキュリティ 管理コンプライアンス センターの組織の管理またはセキュリティ管理者の役割の[&必要があります](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="0dec2-144">手順 1: セキュリティ コンプライアンス センターで検疫&作成する</span><span class="sxs-lookup"><span data-stu-id="0dec2-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="0dec2-145">セキュリティ コンプライアンス センターで&の管理ポリシーに移動し、[検疫 \> タグ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="0dec2-146">[検疫タグ **] ページで** 、[カスタム タグの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="0dec2-147">新 **しいタグ ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="0dec2-148">[タグ名 **] ページで** 、[タグ名] フィールドに簡単で一意の **名前を入力** します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="0dec2-149">今後の手順では、名前でタグを識別して選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dec2-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="0dec2-150">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0dec2-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0dec2-151">[受信者メッセージ **アクセス] ページ** で、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="0dec2-152">**アクセスなし**</span><span class="sxs-lookup"><span data-stu-id="0dec2-152">**No access**</span></span>
   - <span data-ttu-id="0dec2-153">**制限付きアクセス**</span><span class="sxs-lookup"><span data-stu-id="0dec2-153">**Limited access**</span></span>
   - <span data-ttu-id="0dec2-154">**フル アクセス**</span><span class="sxs-lookup"><span data-stu-id="0dec2-154">**Full access**</span></span>

   <span data-ttu-id="0dec2-155">これらのアクセス許可グループに含まれる個々のアクセス許可については、この記事の前で説明します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="0dec2-156">カスタムアクセス許可を指定するには、[特定のアクセス **許可を設定する (Advanced)** を選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="0dec2-157">**[リリース アクションの基本設定]** を選択します。次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="0dec2-158">**リリースアクションなし**: これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="0dec2-159">**受信者が検疫からメッセージを解放するを許可する**</span><span class="sxs-lookup"><span data-stu-id="0dec2-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="0dec2-160">**受信者が検疫からメッセージを解放する要求を許可する**</span><span class="sxs-lookup"><span data-stu-id="0dec2-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="0dec2-161">**検疫済みメッセージに対して** 受信者が実行できる追加のアクションを選択する: 次の値の一部、すべて、またはなしを選択します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="0dec2-162">**削除**</span><span class="sxs-lookup"><span data-stu-id="0dec2-162">**Delete**</span></span>
       - <span data-ttu-id="0dec2-163">**プレビュー**</span><span class="sxs-lookup"><span data-stu-id="0dec2-163">**Preview**</span></span>
       - <span data-ttu-id="0dec2-164">**送信者を許可する**</span><span class="sxs-lookup"><span data-stu-id="0dec2-164">**Allow sender**</span></span>
       - <span data-ttu-id="0dec2-165">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="0dec2-165">**Block sender**</span></span>

   <span data-ttu-id="0dec2-166">これらのアクセス許可と検疫済みメッセージおよびエンド ユーザースパム通知への影響については、この記事の後半の「検疫タグ [のアクセス](#quarantine-tag-permission-details) 許可の詳細」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="0dec2-167">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0dec2-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0dec2-168">表示される **[概要]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="0dec2-169">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0dec2-170">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="0dec2-171">表示 **される確認** ページで [完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0dec2-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="0dec2-172">これで、「手順 2」の説明に従って検疫タグを検疫機能に割り [当てる準備ができました](#step-2-assign-a-quarantine-tag-to-supported-features) 。</span><span class="sxs-lookup"><span data-stu-id="0dec2-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="0dec2-173">PowerShell で検疫タグを作成する</span><span class="sxs-lookup"><span data-stu-id="0dec2-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="0dec2-174">PowerShell を使用して検疫タグを作成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し **、New-QuarantineTag コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="0dec2-175">次の 2 つの方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="0dec2-176">_EndUserQuarantinePermissionsValue パラメーターを使用_ します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="0dec2-177">_EndUserQuarantinePermissions パラメーターを使用_ します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="0dec2-178">これらのメソッドについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="0dec2-179">EndUserQuarantinePermissionsValue パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="0dec2-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="0dec2-180">_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫タグを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="0dec2-181">_EndUserQuarantinePermissionsValue_ パラメーターは、バイナリ値から変換される 10 進値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="0dec2-182">バイナリ値は、特定の順序で使用可能なエンド ユーザー検疫のアクセス許可に対応します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="0dec2-183">アクセス許可ごとに、値 1 は True、値 0 は False に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="0dec2-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="0dec2-184">事前設定されたアクセス許可グループの各アクセス許可に必要な順序と値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="0dec2-185">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="0dec2-185">Permission</span></span>|<span data-ttu-id="0dec2-186">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="0dec2-186">No access</span></span>|<span data-ttu-id="0dec2-187">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-187">Limited access</span></span>|<span data-ttu-id="0dec2-188">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="0dec2-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="0dec2-189">PermissionToAllowSender</span></span>|<span data-ttu-id="0dec2-190">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-190">0</span></span>|<span data-ttu-id="0dec2-191">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-191">0</span></span>|<span data-ttu-id="0dec2-192">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-192">1</span></span>|
|<span data-ttu-id="0dec2-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="0dec2-193">PermissionToBlockSender</span></span>|<span data-ttu-id="0dec2-194">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-194">0</span></span>|<span data-ttu-id="0dec2-195">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-195">1</span></span>|<span data-ttu-id="0dec2-196">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-196">1</span></span>|
|<span data-ttu-id="0dec2-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="0dec2-197">PermissionToDelete</span></span>|<span data-ttu-id="0dec2-198">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-198">0</span></span>|<span data-ttu-id="0dec2-199">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-199">1</span></span>|<span data-ttu-id="0dec2-200">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-200">1</span></span>|
|<span data-ttu-id="0dec2-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0dec2-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="0dec2-202">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-202">0</span></span>|<span data-ttu-id="0dec2-203">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-203">0</span></span>|<span data-ttu-id="0dec2-204">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-204">0</span></span>|
|<span data-ttu-id="0dec2-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="0dec2-205">PermissionToPreview</span></span>|<span data-ttu-id="0dec2-206">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-206">0</span></span>|<span data-ttu-id="0dec2-207">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-207">1</span></span>|<span data-ttu-id="0dec2-208">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-208">1</span></span>|
|<span data-ttu-id="0dec2-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0dec2-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="0dec2-210">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-210">0</span></span>|<span data-ttu-id="0dec2-211">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-211">0</span></span>|<span data-ttu-id="0dec2-212">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-212">1</span></span>|
|<span data-ttu-id="0dec2-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0dec2-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="0dec2-214">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-214">0</span></span>|<span data-ttu-id="0dec2-215">1</span><span class="sxs-lookup"><span data-stu-id="0dec2-215">1</span></span>|<span data-ttu-id="0dec2-216">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-216">0</span></span>|
|<span data-ttu-id="0dec2-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0dec2-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="0dec2-218">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-218">0</span></span>|<span data-ttu-id="0dec2-219">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-219">0</span></span>|<span data-ttu-id="0dec2-220">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-220">0</span></span>|
|<span data-ttu-id="0dec2-221">バイナリ値</span><span class="sxs-lookup"><span data-stu-id="0dec2-221">Binary value</span></span>|<span data-ttu-id="0dec2-222">00000000</span><span class="sxs-lookup"><span data-stu-id="0dec2-222">00000000</span></span>|<span data-ttu-id="0dec2-223">01101010</span><span class="sxs-lookup"><span data-stu-id="0dec2-223">01101010</span></span>|<span data-ttu-id="0dec2-224">11101100</span><span class="sxs-lookup"><span data-stu-id="0dec2-224">11101100</span></span>|
|<span data-ttu-id="0dec2-225">使用する 10 進値</span><span class="sxs-lookup"><span data-stu-id="0dec2-225">Decimal value to use</span></span>|<span data-ttu-id="0dec2-226">0</span><span class="sxs-lookup"><span data-stu-id="0dec2-226">0</span></span>|<span data-ttu-id="0dec2-227">106</span><span class="sxs-lookup"><span data-stu-id="0dec2-227">106</span></span>|<span data-ttu-id="0dec2-228">236</span><span class="sxs-lookup"><span data-stu-id="0dec2-228">236</span></span>|

<span data-ttu-id="0dec2-229"><sup>\*</sup> 現在、この値は常に 0 です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="0dec2-230">PermissionToViewHeader の場合、値 0 は検疫済みメッセージの詳細で [メッセージ ヘッダーの表示] ボタンを非表示にできません (ボタンは常に使用できます)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="0dec2-231"><sup>\*\*</sup> 両方の値を 1 に設定しない。</span><span class="sxs-lookup"><span data-stu-id="0dec2-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="0dec2-232">1 を 1 に、もう一方を 0 に設定するか、両方を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="0dec2-233">次の使用例は、前の表で説明したように、アクセス許可なしを割り当てる新しい検疫タグ名 NoAccess を作成します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="0dec2-234">制限付きアクセス許可の場合は、値 106 を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="0dec2-235">[完全アクセス許可] の場合は、値 236 を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="0dec2-236">カスタムアクセス許可の場合は、前の表を使用して、必要なアクセス許可に対応するバイナリ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="0dec2-237">バイナリ値を 10 進値に変換し _、EndUserQuarantinePermissionsValue_ パラメーターに 10 進値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="0dec2-238">構文とパラメーターの詳細については [、「New-QuarantineTag」を参照してください](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-238">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="0dec2-239">EndUserQuarantinePermissions パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="0dec2-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="0dec2-240">_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫タグを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="0dec2-241">A.</span><span class="sxs-lookup"><span data-stu-id="0dec2-241">A.</span></span> <span data-ttu-id="0dec2-242">**New-QuarantinePermissions** コマンドレットを使用して、検疫アクセス許可オブジェクトを変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="0dec2-243">B.</span><span class="sxs-lookup"><span data-stu-id="0dec2-243">B.</span></span> <span data-ttu-id="0dec2-244">New-QuarantineTag コマンドの _EndUserQuarantinePermissions_ 値 **として変数を使用** します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="0dec2-245">手順 A: 検疫アクセス許可オブジェクトを変数に格納する</span><span class="sxs-lookup"><span data-stu-id="0dec2-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="0dec2-246">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="0dec2-247">未使用のパラメーターの既定値は次の値なので、値をに設定するパラメーターのみを `$false` 使用する必要があります `$true` 。</span><span class="sxs-lookup"><span data-stu-id="0dec2-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="0dec2-248">次の例は、事前設定されたアクセス許可グループに対応するアクセス許可オブジェクトを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0dec2-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="0dec2-249">**アクセスなし**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="0dec2-250">**制限付きアクセス**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="0dec2-251">**フル アクセス**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="0dec2-252">設定した値を表示するには、変数名をコマンドとして実行します (たとえば、コマンドを実行します `$NoAccess` )。</span><span class="sxs-lookup"><span data-stu-id="0dec2-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="0dec2-253">カスタムアクセス許可の場合は _、PermissionToRelease_ パラメーターと _PermissionToRequestRelease_ パラメーターの両方をに設定しない `$true` 。</span><span class="sxs-lookup"><span data-stu-id="0dec2-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="0dec2-254">1 つを `$true` に設定し、もう一方を `$false` そのままにするか、両方をとして残します `$false` 。</span><span class="sxs-lookup"><span data-stu-id="0dec2-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="0dec2-255">作成後 **、Set-QuarantinePermissions** コマンドレットを使用して使用する前に、既存のアクセス許可オブジェクト変数を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="0dec2-256">構文とパラメーターの詳細については [、「New-QuarantinePermissions」](/powershell/module/exchange/new-quarantinepermissions) および [「Set-QuarantinePermissions」を参照してください](/powershell/module/exchange/set-quarantinepermissions)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="0dec2-257">手順 B: [変数] コマンドで変数New-QuarantineTagします。</span><span class="sxs-lookup"><span data-stu-id="0dec2-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="0dec2-258">permissions オブジェクトを変数に作成して格納したら、次の **New-QuarantineTag** コマンドで _EndUserQuarantinePermission_ パラメーター値の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="0dec2-259">この例では、前の手順で説明して作成した permissions オブジェクトを使用して、LimitedAccess という名前の新しい検疫 `$LimitedAccess` タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="0dec2-260">構文とパラメーターの詳細については [、「New-QuarantineTag」を参照してください](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-260">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="0dec2-261">手順 2: サポートされている機能に検疫タグを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0dec2-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="0dec2-262">メッセージ _またはファイルを_ 検疫するサポートされている保護機能 (自動的に、または構成可能なアクションとして) では、検疫タグを使用可能な検疫アクションに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="0dec2-263">メッセージを検疫する機能と検疫タグの可用性については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="0dec2-264">特徴</span><span class="sxs-lookup"><span data-stu-id="0dec2-264">Feature</span></span>|<span data-ttu-id="0dec2-265">検疫タグがサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="0dec2-265">Quarantine tags supported?</span></span>|<span data-ttu-id="0dec2-266">使用される既定の検疫タグ</span><span class="sxs-lookup"><span data-stu-id="0dec2-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="0dec2-267">[スパム対策ポリシー](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="0dec2-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="0dec2-268">**スパム** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="0dec2-269">**高信頼スパム** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="0dec2-270">**フィッシングメール** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="0dec2-271">**高信頼フィッシング メール** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="0dec2-272">**バルク メール** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="0dec2-273">はい</span><span class="sxs-lookup"><span data-stu-id="0dec2-273">Yes</span></span>|<ul><li><span data-ttu-id="0dec2-274">DefaultSpamTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="0dec2-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="0dec2-275">DefaultHighConfSpamTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="0dec2-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="0dec2-276">DefaultPhishTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="0dec2-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="0dec2-277">DefaultHighConfPhishTag (アクセスなし)</span><span class="sxs-lookup"><span data-stu-id="0dec2-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="0dec2-278">DefaultBulkTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="0dec2-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="0dec2-279">フィッシング対策ポリシー:</span><span class="sxs-lookup"><span data-stu-id="0dec2-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="0dec2-280">[スプーフィング インテリジェンス保護](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="0dec2-281">[偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0dec2-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="0dec2-282">**偽装ユーザーによって電子メールが送信** された場合 (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="0dec2-283">**偽装ドメイン**_(TargetedDomainProtectionAction) によって電子メールが送信される場合_</span><span class="sxs-lookup"><span data-stu-id="0dec2-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="0dec2-284">**メールボックス インテリジェンス** \>**偽装ユーザーからメールが送信された場合**(_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="0dec2-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="0dec2-285">いいえ</span><span class="sxs-lookup"><span data-stu-id="0dec2-285">No</span></span>|<span data-ttu-id="0dec2-286">該当なし</span><span class="sxs-lookup"><span data-stu-id="0dec2-286">n/a</span></span>|
|<span data-ttu-id="0dec2-287">[マルウェア対策ポリシー](configure-anti-malware-policies.md): 検出されたメッセージはすべて常に検疫されます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="0dec2-288">いいえ</span><span class="sxs-lookup"><span data-stu-id="0dec2-288">No</span></span>|<span data-ttu-id="0dec2-289">該当なし</span><span class="sxs-lookup"><span data-stu-id="0dec2-289">n/a</span></span>|
|[<span data-ttu-id="0dec2-290">SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="0dec2-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="0dec2-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="0dec2-291">No</span></span>|<span data-ttu-id="0dec2-292">該当なし</span><span class="sxs-lookup"><span data-stu-id="0dec2-292">n/a</span></span>|
|<span data-ttu-id="0dec2-293">[アクションを含む](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) メール フロー ルール (トランスポート ルールとも呼ばれる): メッセージをホストされた検疫 (検疫) **に** 配信 _します_。</span><span class="sxs-lookup"><span data-stu-id="0dec2-293">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="0dec2-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="0dec2-294">No</span></span>|<span data-ttu-id="0dec2-295">該当なし</span><span class="sxs-lookup"><span data-stu-id="0dec2-295">n/a</span></span>|
|

<span data-ttu-id="0dec2-296"><sup>\*</sup> 偽装保護の設定は、Microsoft Defender のフィッシング対策ポリシー (365) でのみOfficeできます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="0dec2-297">既定の検疫タグによって提供されるエンド ユーザーのアクセス許可に満足している場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="0dec2-298">エンド ユーザーのスパム通知または検疫済みメッセージの詳細でエンド ユーザー機能 (使用可能なボタン) をカスタマイズする場合は、カスタム検疫タグを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="0dec2-299">セキュリティ コンプライアンス センターでスパム対策ポリシーに検疫タグ&割り当てる</span><span class="sxs-lookup"><span data-stu-id="0dec2-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="0dec2-300">スパム対策ポリシーを作成および変更する手順の詳細については、「EOP でのスパム対策ポリシーの構成」 [を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="0dec2-301">セキュリティ コンプライアンス センターで、[&管理ポリシー]に移動し、[ \>  \> スパム対策]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="0dec2-302">または、 を開きます <https://protection.office.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="0dec2-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="0dec2-303">編集する既存のスパム対策ポリシーを検索して選択するか、新しいスパム対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="0dec2-304">ポリシーの詳細フライアウトで、[スパムと一括 **アクション] セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="0dec2-305">使用可能なスパム フィルターの評決のアクションに対して [検疫メッセージ] を選択した場合は、[検疫ポリシーの適用] タグ ボックスを使用して、その評決の検疫タグを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="0dec2-306">**注**: 新しいポリシーを作成すると、スパム フィルターの評決に対する空白の検疫タグ値は、その評決の既定の検疫タグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="0dec2-307">後でポリシーを編集すると、前の表で説明したように、空白の値は実際の既定の検疫タグ名に置き換えられる。</span><span class="sxs-lookup"><span data-stu-id="0dec2-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![スパム対策ポリシーの検疫タグの選択](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="0dec2-309">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0dec2-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="0dec2-310">PowerShell のスパム対策ポリシーで検疫タグを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0dec2-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="0dec2-311">スパム対策ポリシーで検疫タグを割り当てる場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="0dec2-312">**注**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-312">**Notes**:</span></span>

- <span data-ttu-id="0dec2-313">_HighConfidencePhishAction_ パラメーターの既定値は [検疫] なので、新しいスパム対策ポリシーで高信頼フィッシング検出の検疫アクションを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="0dec2-314">新しいスパム対策ポリシーまたは既存のスパム対策ポリシーの他のすべてのスパム フィルターの評決では、検疫タグは、アクション値が [検疫] の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="0dec2-315">既存のスパム対策ポリシーのアクション値を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="0dec2-316">Standard および Strict の既定のアクション値と推奨されるアクション値については、「EOP スパム対策ポリシー設定」 [を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="0dec2-317">対応する検疫タグ パラメーターのないスパム フィルターの評決は、[](#step-2-assign-a-quarantine-tag-to-supported-features)その評決の既定の検疫タグが使用されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="0dec2-318">検疫済みメッセージの既定のエンド ユーザー機能を変更する場合は、既定の検疫タグをカスタム検疫タグに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dec2-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="0dec2-319">PowerShell の新しいスパム対策ポリシーには **、New-HostedContentFilterPolicy** コマンドレットを使用するスパム フィルター ポリシー (設定) と **、New-HostedContentFilterRule** コマンドレットを使用する新しいスパム フィルター ルール (受信者フィルター) が必要です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="0dec2-320">手順については [、「Use PowerShell を使用してスパム対策ポリシーを作成する」を参照してください](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="0dec2-321">この例では、次の設定を使用して、Research Department という名前の新しいスパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="0dec2-322">すべてのスパム フィルターの評決に対するアクションが [検疫] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="0dec2-323">アクセス許可なしを割り当てる NoAccess という名前のカスタム検疫タグは、既定でアクセス許可を割り当てない既定の検疫タグに置き換わります。 </span><span class="sxs-lookup"><span data-stu-id="0dec2-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="0dec2-324">構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="0dec2-325">この例では、Human Resources という名前の既存のスパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="0dec2-326">スパム検疫の評決のアクションは [検疫] に設定され、NoAccess という名前のカスタム検疫タグが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="0dec2-327">構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="0dec2-328">セキュリティ ポリシー コンプライアンス センターでグローバル検疫通知&構成する</span><span class="sxs-lookup"><span data-stu-id="0dec2-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="0dec2-329">検疫タグのグローバル設定を使用すると、検疫されたメッセージの受信者に送信されるエンドユーザーのスパム通知をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="0dec2-330">これらの通知の詳細については、「エンドユーザーの [スパム通知」を参照してください](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="0dec2-331">セキュリティ コンプライアンス センターで&の管理ポリシーに移動し、[検疫 \> タグ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="0dec2-332">[検疫タグ **] ページで** 、[グローバル設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="0dec2-333">開く **検疫通知設定の** フライアウトで、次の設定の一部またはすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="0dec2-334">**[会社のロゴを使用** する]: エンド ユーザーのスパム通知の上部で使用される既定の Microsoft ロゴを置き換える場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="0dec2-335">これを行う前に、「組織の [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) テーマをカスタマイズしてカスタム ロゴをアップロードする」の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dec2-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="0dec2-336">次のスクリーンショットは、エンドユーザーのスパム通知のカスタム ロゴを示しています。</span><span class="sxs-lookup"><span data-stu-id="0dec2-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![エンドユーザースパム通知のカスタム ロゴ](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="0dec2-338">**[言語の選択**]: エンド ユーザーのスパム通知は、受信者の言語設定に基づいて既にローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="0dec2-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="0dec2-339">表示名と免責事項の値には、異なる **言語でカスタマイズ** されたテキスト **を指定** できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="0dec2-340">[最初の言語] ボックスから少なくとも 1 つの言語を選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="0dec2-341">複数の言語を選択するには、[追加] をクリック **します** 。</span><span class="sxs-lookup"><span data-stu-id="0dec2-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="0dec2-342">セクションの言語ボックスには、選択した言語すべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-342">A section language box shows all of the languages that you've selected:</span></span>

     ![検疫タグのグローバル検疫通知設定の [2 番目の言語] ボックスで選択した言語](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="0dec2-344">**表示名**: エンド ユーザーのスパム通知で使用される送信者の表示名をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="0dec2-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="0dec2-345">追加した言語ごとに、2 番目の言語ボックス ([X] をクリックしない) で言語を選択し、[表示名] ボックスに必要なテキスト値 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="0dec2-346">次のスクリーンショットは、エンド ユーザーのスパム通知でカスタマイズされた表示名を示しています。</span><span class="sxs-lookup"><span data-stu-id="0dec2-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![エンド ユーザースパム通知のカスタマイズされた送信者の表示名](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="0dec2-348">**免責** 事項 : エンドユーザーのスパム通知の下部にカスタム免責事項を追加します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="0dec2-349">ローカライズされたテキスト、 **組織からの免責事項:** は常に最初に含まれていて、その後に指定したテキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="0dec2-350">追加した言語ごとに、2 番目の言語ボックス ([X] をクリックしない) で言語を選択し、[免責事項] ボックスに必要なテキスト値 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="0dec2-351">次のスクリーンショットは、エンド ユーザーのスパム通知でカスタマイズされた免責事項を示しています。</span><span class="sxs-lookup"><span data-stu-id="0dec2-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![エンドユーザーのスパム通知の下部にあるカスタム免責事項](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="0dec2-353">セキュリティ コンプライアンス センターで検疫タグ&表示する</span><span class="sxs-lookup"><span data-stu-id="0dec2-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="0dec2-354">セキュリティ コンプライアンス センターで&の管理ポリシーに移動し、[検疫 \> タグ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="0dec2-355">組み込みまたはカスタム検疫タグの設定を表示するには、リストから検疫タグを選択します (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="0dec2-356">グローバル設定を表示するには、[グローバル設定] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="0dec2-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="0dec2-357">PowerShell で検疫タグを表示する</span><span class="sxs-lookup"><span data-stu-id="0dec2-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="0dec2-358">PowerShell を使用して検疫タグを表示する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="0dec2-359">すべての組み込みタグまたはカスタム タグの概要リストを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="0dec2-360">組み込みまたはカスタム検疫タグの設定を表示するには、検疫タグの名前に置き換え、 \<TagName\> 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="0dec2-361">グローバル設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="0dec2-362">構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="0dec2-363">セキュリティ コンプライアンス センターで検疫タグ&削除する</span><span class="sxs-lookup"><span data-stu-id="0dec2-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="0dec2-364">**注**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-364">**Notes**:</span></span>

- <span data-ttu-id="0dec2-365">組み込みの検疫タグは削除できない。</span><span class="sxs-lookup"><span data-stu-id="0dec2-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="0dec2-366">カスタム検疫タグを削除する前に、使用されていないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="0dec2-367">たとえば、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="0dec2-368">検疫タグが使用されている場合は、割 [り当てられた検疫タグを](#step-2-assign-a-quarantine-tag-to-supported-features) 削除する前に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dec2-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="0dec2-369">セキュリティ コンプライアンス センターで&の管理ポリシーに移動し、[検疫 \> タグ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="0dec2-370">[検疫タグ **] ページ** で、削除するカスタム検疫タグを選択し、[タグの削除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0dec2-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="0dec2-371">表示 **される確認ダイアログ** で [タグの削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0dec2-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="0dec2-372">PowerShell で検疫タグを削除する</span><span class="sxs-lookup"><span data-stu-id="0dec2-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="0dec2-373">PowerShell を使用してカスタム検疫タグを削除する場合は、検疫タグの名前に置き換え、次の \<TagName\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="0dec2-374">構文とパラメーターの詳細については [、「Remove-QuarantineTag」を参照してください](/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="0dec2-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="0dec2-375">検疫タグのアクセス許可の詳細</span><span class="sxs-lookup"><span data-stu-id="0dec2-375">Quarantine tag permission details</span></span>

<span data-ttu-id="0dec2-376">次のセクションでは、検疫済みメッセージの詳細およびエンドユーザーのスパム通知における事前設定されたアクセス許可グループと個々のアクセス許可の影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="0dec2-377">事前設定されたアクセス許可グループ</span><span class="sxs-lookup"><span data-stu-id="0dec2-377">Preset permissions groups</span></span>

<span data-ttu-id="0dec2-378">事前設定されたアクセス許可グループに含まれる個々のアクセス許可は、この記事の冒頭の表に示されています。</span><span class="sxs-lookup"><span data-stu-id="0dec2-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="0dec2-379">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="0dec2-379">No access</span></span>

<span data-ttu-id="0dec2-380">検疫タグがアクセス許可なし(アクセス許可なし) を割り当てる場合、ユーザーは引き続きいくつかのベースライン機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="0dec2-381">**検疫済みメッセージの詳細**: [ **メッセージ ヘッダーの表示] ボタン** は常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![検疫タグによってユーザーにアクセス許可がない場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="0dec2-383">**エンドユーザーのスパム通知**: **検疫内** のメッセージにユーザーを移動する [確認] ボタンは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![検疫タグによってユーザーにアクセス許可がない場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="0dec2-385">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-385">Limited access</span></span>

<span data-ttu-id="0dec2-386">検疫タグに制限付きアクセス許可 **が割り** 当てられている場合、ユーザーは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="0dec2-387">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="0dec2-388">**リリースの要求**</span><span class="sxs-lookup"><span data-stu-id="0dec2-388">**Request release**</span></span>
  - <span data-ttu-id="0dec2-389">**メッセージ ヘッダーの表示**</span><span class="sxs-lookup"><span data-stu-id="0dec2-389">**View message header**</span></span>
  - <span data-ttu-id="0dec2-390">**プレビュー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="0dec2-390">**Preview message**</span></span>
  - <span data-ttu-id="0dec2-391">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="0dec2-391">**Block sender**</span></span>
  - <span data-ttu-id="0dec2-392">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="0dec2-392">**Remove from quarantine**</span></span>

  ![検疫タグがユーザーに制限付きアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="0dec2-394">**エンド ユーザーのスパム通知**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="0dec2-395">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="0dec2-395">**Block sender**</span></span>
  - <span data-ttu-id="0dec2-396">**確認**</span><span class="sxs-lookup"><span data-stu-id="0dec2-396">**Review**</span></span>

  ![検疫タグがユーザーに制限付きアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="0dec2-398">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="0dec2-398">Full access</span></span>

<span data-ttu-id="0dec2-399">検疫タグがフル アクセス権限(すべての使用可能なアクセス許可) を割り当てる場合、ユーザーは次の機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="0dec2-400">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="0dec2-401">**リリース メッセージ**</span><span class="sxs-lookup"><span data-stu-id="0dec2-401">**Release message**</span></span>
  - <span data-ttu-id="0dec2-402">**メッセージ ヘッダーの表示**</span><span class="sxs-lookup"><span data-stu-id="0dec2-402">**View message header**</span></span>
  - <span data-ttu-id="0dec2-403">**プレビュー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="0dec2-403">**Preview message**</span></span>
  - <span data-ttu-id="0dec2-404">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="0dec2-404">**Block sender**</span></span>
  - <span data-ttu-id="0dec2-405">**送信者を許可する**</span><span class="sxs-lookup"><span data-stu-id="0dec2-405">**Allow sender**</span></span>
  - <span data-ttu-id="0dec2-406">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="0dec2-406">**Remove from quarantine**</span></span>

  ![検疫タグがユーザーにフル アクセスのアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="0dec2-408">**エンド ユーザーのスパム通知**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="0dec2-409">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="0dec2-409">**Block sender**</span></span>
  - <span data-ttu-id="0dec2-410">**Release**</span><span class="sxs-lookup"><span data-stu-id="0dec2-410">**Release**</span></span>
  - <span data-ttu-id="0dec2-411">**確認**</span><span class="sxs-lookup"><span data-stu-id="0dec2-411">**Review**</span></span>

  ![検疫タグがユーザーにフル アクセスのアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="0dec2-413">個々のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0dec2-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="0dec2-414">ユーザーは、[アクセスなし] セクションで説明されているボタンを常 [に取得](#no-access) します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="0dec2-415">これらのボタンは、個々のアクセス許可の説明には含まれません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="0dec2-416">送信者のアクセス許可を許可する</span><span class="sxs-lookup"><span data-stu-id="0dec2-416">Allow sender permission</span></span>

<span data-ttu-id="0dec2-417">[ **送信者の許可** ]_(PermissionToAllowSender)_ は、検疫済みメッセージ送信者を自分の差出人セーフ リストに簡単に追加できるボタンへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="0dec2-418">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="0dec2-419">**[送信者のアクセス許可** を有効にする]: [送信者 **を許可する** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="0dec2-420">**[送信者のアクセス許可** を無効にする]: [送信者 **を許可する** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="0dec2-421">**エンド ユーザーのスパム通知**: 無効です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="0dec2-422">差出人セーフ リストの詳細については、「信頼[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)できる送信者がブロックされるのを防ぐ」および[「Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスでセーフリスト コレクションを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="0dec2-423">送信者のアクセス許可をブロックする</span><span class="sxs-lookup"><span data-stu-id="0dec2-423">Block sender permission</span></span>

<span data-ttu-id="0dec2-424">[ **送信者のブロック]** アクセス許可 _(PermissionToBlockSender)_ はボタンへのアクセスを制御し、検疫済みメッセージ送信者をブロックされた送信者リストに簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="0dec2-425">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="0dec2-426">**[送信者のアクセス許可** をブロックする] を有効にする: **[送信者のブロック** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="0dec2-427">**[送信者のアクセス許可** を無効にする]: [ **送信者のブロック** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="0dec2-428">**エンド ユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="0dec2-429">**[送信者のアクセス許可** を無効にする]: [ **送信者のブロック** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="0dec2-430">**[送信者のアクセス許可** をブロックする] を有効にする: **[送信者のブロック** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="0dec2-431">[送信者のブロック] リストの詳細については、「他[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)のユーザーからのメッセージをブロックする」および[「Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスでセーフリスト コレクションを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dec2-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="0dec2-432">削除のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0dec2-432">Delete permission</span></span>

<span data-ttu-id="0dec2-433">[ **削除]** アクセス許可 _(PermissionToDelete)_ は、ユーザーが検疫からメッセージ (ユーザーが受信者であるメッセージ) を削除する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="0dec2-434">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="0dec2-435">**アクセス許可** の削除が有効: [ **検疫から削除] ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="0dec2-436">**削除** のアクセス許可が無効: [ **検疫から削除] ボタン** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="0dec2-437">**エンド ユーザーのスパム通知**: 無効です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="0dec2-438">プレビューのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0dec2-438">Preview permission</span></span>

<span data-ttu-id="0dec2-439">[ **プレビュー]** アクセス許可 _(PermissionToPreview)_ は、ユーザーが検疫でメッセージをプレビューする機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="0dec2-440">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="0dec2-441">**プレビュー** のアクセス許可が有効: **[メッセージのプレビュー] ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="0dec2-442">**プレビュー** のアクセス許可が無効: **[メッセージのプレビュー]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="0dec2-443">**エンド ユーザーのスパム通知**: 無効です。</span><span class="sxs-lookup"><span data-stu-id="0dec2-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="0dec2-444">受信者が検疫のアクセス許可からメッセージを解放するを許可する</span><span class="sxs-lookup"><span data-stu-id="0dec2-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="0dec2-445">[ **受信者に検疫** からのメッセージの解放を許可する] アクセス許可 _(PermissionToRelease)_ は、ユーザーが管理者の承認なしに検疫済みメッセージを直接解放する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="0dec2-446">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="0dec2-447">アクセス許可が有効: **[メッセージの解放] ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="0dec2-448">アクセス許可が無効: **[メッセージの解放]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="0dec2-449">**エンド ユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="0dec2-450">アクセス許可が有効: **[リリース]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="0dec2-451">アクセス許可が無効: **[リリース]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="0dec2-452">受信者が検疫アクセス許可からメッセージを解放する要求を許可する</span><span class="sxs-lookup"><span data-stu-id="0dec2-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="0dec2-453">[**受信者に検疫** からのメッセージの解放を要求する] アクセス許可 _(PermissionToRequestRelease)_ は、ユーザーが検疫済みメッセージのリリースを要求する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="0dec2-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="0dec2-454">メッセージは、管理者が要求を承認した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="0dec2-455">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="0dec2-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="0dec2-456">アクセス許可が有効: **[要求] リリース ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dec2-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="0dec2-457">アクセス許可が無効: **[要求] リリース** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="0dec2-458">**エンドユーザーのスパム通知**: [ **リリース] ボタン** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0dec2-458">**End-user spam notifications**: The **Release** button is not available.</span></span>