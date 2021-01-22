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
description: 管理者は、検疫タグを使用して、ユーザーが検疫済みメッセージに対して実行できる操作を制御する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f18ad6ce1c8b12d38aef377ab663ca679a703e5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928904"
---
# <a name="quarantine-tags"></a><span data-ttu-id="89763-103">検疫タグ</span><span class="sxs-lookup"><span data-stu-id="89763-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="89763-104">この記事で説明する機能は現在プレビュー中であり、すべてのユーザーが利用できる機能ではありません。また、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89763-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="89763-105">Exchange Online Protection (EOP) の検疫タグを使用すると、管理者は、メッセージが検疫に到着した方法に基づいて、ユーザーが検疫済みメッセージに対して実行できる操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="89763-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="89763-106">EOP は、従来、検疫内のメッセージとエンド ユーザーのスパム通知[](find-and-release-quarantined-messages-as-a-user.md)で、特定のレベルの対話機能を許可または[防止しました](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="89763-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="89763-107">たとえば、エンドユーザーはスパム対策フィルターによって検疫されたメッセージをスパムまたはバルクとして表示および解放できますが、信頼度の高いフィッシングとして検疫されたメッセージを表示または解放したりは行えなくなります。</span><span class="sxs-lookup"><span data-stu-id="89763-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="89763-108">サポート [されている](#step-2-assign-a-quarantine-tag-to-supported-features)保護機能の場合、検疫タグは、エンド ユーザーのスパム通知メッセージおよび検疫済みメッセージ (ユーザーが受信者であるメッセージ) でユーザーが実行できる操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="89763-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="89763-109">既定の検疫タグは、エンドユーザーに対して検疫済みメッセージの履歴機能を適用するために自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="89763-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="89763-110">または、カスタム検疫タグを作成して割り当て、エンド ユーザーが検疫済みメッセージに対して特定の操作を実行する許可または防止を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="89763-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="89763-111">個々のアクセス許可は、次の事前設定されたアクセス許可グループに結合されます。</span><span class="sxs-lookup"><span data-stu-id="89763-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="89763-112">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="89763-112">No access</span></span>
- <span data-ttu-id="89763-113">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89763-113">Limited access</span></span>
- <span data-ttu-id="89763-114">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="89763-114">Full access</span></span>

<span data-ttu-id="89763-115">使用可能な個々のアクセス許可と、既定のアクセス許可グループに含まれるもの、または含まれていないものについて、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="89763-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="89763-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="89763-116">Permission</span></span>|<span data-ttu-id="89763-117">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="89763-117">No access</span></span>|<span data-ttu-id="89763-118">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89763-118">Limited access</span></span>|<span data-ttu-id="89763-119">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="89763-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="89763-120">**送信者を許可** する (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="89763-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="89763-122">**送信者をブロック** する (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="89763-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="89763-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="89763-125">**Delete** (_PermissionToDelete_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="89763-128">**Preview** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="89763-128">**Preview** (_PermissionToPreview_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="89763-131">**受信者が検疫からメッセージを解放する** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="89763-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="89763-133">**受信者に検疫からのメッセージの解放を要求する** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="89763-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![チェック マーク](../../media/checkmark.png)||
|

<span data-ttu-id="89763-135">既定のアクセス許可グループの既定のアクセス許可が気に入らない場合は、カスタム検疫タグを作成または変更するときにカスタムアクセス許可を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="89763-136">各アクセス許可の機能の詳細については、この記事の後半の「 [検疫タグのアクセス許可の](#quarantine-tag-permission-details) 詳細」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="89763-137">検疫タグは、セキュリティ & コンプライアンス センターまたは PowerShell で作成して割り当てる必要があります (Exchange Online メールボックスを使用する Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない EOP 組織のスタンドアロン EOP PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="89763-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="89763-138">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="89763-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="89763-139"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="89763-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="89763-140">[検疫タグ] ページに **直接移動するには** 、開きます <https://protection.office.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="89763-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="89763-141">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="89763-142">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="89763-143">検疫タグを表示、作成、変更、または削除するには、セキュリティ/コンプライアンス センターの組織の管理またはセキュリティ管理者の役割の[メンバー&必要があります](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="89763-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="89763-144">手順 1: セキュリティ/コンプライアンス センターで検疫&作成する</span><span class="sxs-lookup"><span data-stu-id="89763-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="89763-145">セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="89763-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="89763-146">[検疫タグ **] ページで** 、[カスタム タグの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89763-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="89763-147">新 **しいタグ ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="89763-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="89763-148">[タグ **名] ページ** で、[タグ名] フィールドに一意の名前 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="89763-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="89763-149">今後の手順では、名前でタグを識別して選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89763-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="89763-150">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89763-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="89763-151">[受信者 **メッセージ アクセス] ページ** で、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="89763-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="89763-152">**アクセスなし**</span><span class="sxs-lookup"><span data-stu-id="89763-152">**No access**</span></span>
   - <span data-ttu-id="89763-153">**制限付きアクセス**</span><span class="sxs-lookup"><span data-stu-id="89763-153">**Limited access**</span></span>
   - <span data-ttu-id="89763-154">**フル アクセス**</span><span class="sxs-lookup"><span data-stu-id="89763-154">**Full access**</span></span>

   <span data-ttu-id="89763-155">これらのアクセス許可グループに含まれる個々のアクセス許可については、この記事で前述しました。</span><span class="sxs-lookup"><span data-stu-id="89763-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="89763-156">カスタムアクセス許可を指定するには、[特定のアクセス **許可を設定する (詳細)** を選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="89763-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="89763-157">**[リリースアクションの基本設定**] を選択します。次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="89763-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="89763-158">**リリース操作なし**: これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="89763-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="89763-159">**受信者による検疫からのメッセージの解放を許可する**</span><span class="sxs-lookup"><span data-stu-id="89763-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="89763-160">**受信者が検疫から解放されるメッセージを要求する**</span><span class="sxs-lookup"><span data-stu-id="89763-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="89763-161">**検疫済みメッセージに対して** 受信者が実行できるその他のアクションを選択する: 次の値の一部、すべて、またはなしを選択します。</span><span class="sxs-lookup"><span data-stu-id="89763-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="89763-162">**Delete**</span><span class="sxs-lookup"><span data-stu-id="89763-162">**Delete**</span></span>
       - <span data-ttu-id="89763-163">**プレビュー**</span><span class="sxs-lookup"><span data-stu-id="89763-163">**Preview**</span></span>
       - <span data-ttu-id="89763-164">**送信者を許可する**</span><span class="sxs-lookup"><span data-stu-id="89763-164">**Allow sender**</span></span>
       - <span data-ttu-id="89763-165">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="89763-165">**Block sender**</span></span>

   <span data-ttu-id="89763-166">これらのアクセス許可とその影響が検疫済みメッセージおよびエンド ユーザーのスパム通知に及ぼす影響については、この記事で後述する「検疫 [タグ](#quarantine-tag-permission-details) のアクセス許可の詳細」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="89763-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="89763-167">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89763-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="89763-168">表示される **[概要]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="89763-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="89763-169">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="89763-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="89763-170">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="89763-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="89763-171">表示 **される確認** ページで [完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89763-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="89763-172">これで、手順 2 のセクションで説明するように、検疫タグを検疫 [機能に割り当てる準備ができました](#step-2-assign-a-quarantine-tag-to-supported-features) 。</span><span class="sxs-lookup"><span data-stu-id="89763-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="89763-173">PowerShell で検疫タグを作成する</span><span class="sxs-lookup"><span data-stu-id="89763-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="89763-174">PowerShell を使用して検疫タグを作成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し **、New-QuarantineTag コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="89763-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="89763-175">次の 2 つの方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="89763-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="89763-176">_EndUserQuarantinePermissionsValue パラメーターを使用_ します。</span><span class="sxs-lookup"><span data-stu-id="89763-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="89763-177">_EndUserQuarantinePermissions パラメーターを使用_ します。</span><span class="sxs-lookup"><span data-stu-id="89763-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="89763-178">これらのメソッドについては、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="89763-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="89763-179">EndUserQuarantinePermissionsValue パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="89763-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="89763-180">_EndUserQuarantinePermissionsValue パラメーター_ を使用して検疫タグを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89763-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="89763-181">_EndUserQuarantinePermissionsValue_ パラメーターは、バイナリ値から変換された 10 進値を使用します。</span><span class="sxs-lookup"><span data-stu-id="89763-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="89763-182">バイナリ値は、使用可能なエンド ユーザーによる検疫のアクセス許可に特定の順序で対応します。</span><span class="sxs-lookup"><span data-stu-id="89763-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="89763-183">アクセス許可ごとに、値 1 は True、値 0 は False に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="89763-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="89763-184">事前設定されたアクセス許可グループの個々のアクセス許可に必要な順序と値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="89763-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="89763-185">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="89763-185">Permission</span></span>|<span data-ttu-id="89763-186">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="89763-186">No access</span></span>|<span data-ttu-id="89763-187">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89763-187">Limited access</span></span>|<span data-ttu-id="89763-188">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="89763-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="89763-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="89763-189">PermissionToAllowSender</span></span>|<span data-ttu-id="89763-190">0</span><span class="sxs-lookup"><span data-stu-id="89763-190">0</span></span>|<span data-ttu-id="89763-191">0</span><span class="sxs-lookup"><span data-stu-id="89763-191">0</span></span>|<span data-ttu-id="89763-192">1 </span><span class="sxs-lookup"><span data-stu-id="89763-192">1</span></span>|
|<span data-ttu-id="89763-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="89763-193">PermissionToBlockSender</span></span>|<span data-ttu-id="89763-194">0</span><span class="sxs-lookup"><span data-stu-id="89763-194">0</span></span>|<span data-ttu-id="89763-195">1 </span><span class="sxs-lookup"><span data-stu-id="89763-195">1</span></span>|<span data-ttu-id="89763-196">1 </span><span class="sxs-lookup"><span data-stu-id="89763-196">1</span></span>|
|<span data-ttu-id="89763-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="89763-197">PermissionToDelete</span></span>|<span data-ttu-id="89763-198">0</span><span class="sxs-lookup"><span data-stu-id="89763-198">0</span></span>|<span data-ttu-id="89763-199">1 </span><span class="sxs-lookup"><span data-stu-id="89763-199">1</span></span>|<span data-ttu-id="89763-200">1 </span><span class="sxs-lookup"><span data-stu-id="89763-200">1</span></span>|
|<span data-ttu-id="89763-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="89763-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="89763-202">0</span><span class="sxs-lookup"><span data-stu-id="89763-202">0</span></span>|<span data-ttu-id="89763-203">0</span><span class="sxs-lookup"><span data-stu-id="89763-203">0</span></span>|<span data-ttu-id="89763-204">0</span><span class="sxs-lookup"><span data-stu-id="89763-204">0</span></span>|
|<span data-ttu-id="89763-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="89763-205">PermissionToPreview</span></span>|<span data-ttu-id="89763-206">0</span><span class="sxs-lookup"><span data-stu-id="89763-206">0</span></span>|<span data-ttu-id="89763-207">1 </span><span class="sxs-lookup"><span data-stu-id="89763-207">1</span></span>|<span data-ttu-id="89763-208">1 </span><span class="sxs-lookup"><span data-stu-id="89763-208">1</span></span>|
|<span data-ttu-id="89763-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="89763-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="89763-210">0</span><span class="sxs-lookup"><span data-stu-id="89763-210">0</span></span>|<span data-ttu-id="89763-211">0</span><span class="sxs-lookup"><span data-stu-id="89763-211">0</span></span>|<span data-ttu-id="89763-212">1 </span><span class="sxs-lookup"><span data-stu-id="89763-212">1</span></span>|
|<span data-ttu-id="89763-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="89763-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="89763-214">0</span><span class="sxs-lookup"><span data-stu-id="89763-214">0</span></span>|<span data-ttu-id="89763-215">1 </span><span class="sxs-lookup"><span data-stu-id="89763-215">1</span></span>|<span data-ttu-id="89763-216">0</span><span class="sxs-lookup"><span data-stu-id="89763-216">0</span></span>|
|<span data-ttu-id="89763-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="89763-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="89763-218">0</span><span class="sxs-lookup"><span data-stu-id="89763-218">0</span></span>|<span data-ttu-id="89763-219">0</span><span class="sxs-lookup"><span data-stu-id="89763-219">0</span></span>|<span data-ttu-id="89763-220">0</span><span class="sxs-lookup"><span data-stu-id="89763-220">0</span></span>|
|<span data-ttu-id="89763-221">バイナリ値</span><span class="sxs-lookup"><span data-stu-id="89763-221">Binary value</span></span>|<span data-ttu-id="89763-222">00000000</span><span class="sxs-lookup"><span data-stu-id="89763-222">00000000</span></span>|<span data-ttu-id="89763-223">01101010</span><span class="sxs-lookup"><span data-stu-id="89763-223">01101010</span></span>|<span data-ttu-id="89763-224">11101100</span><span class="sxs-lookup"><span data-stu-id="89763-224">11101100</span></span>|
|<span data-ttu-id="89763-225">使用する 10 進値</span><span class="sxs-lookup"><span data-stu-id="89763-225">Decimal value to use</span></span>|<span data-ttu-id="89763-226">0</span><span class="sxs-lookup"><span data-stu-id="89763-226">0</span></span>|<span data-ttu-id="89763-227">106</span><span class="sxs-lookup"><span data-stu-id="89763-227">106</span></span>|<span data-ttu-id="89763-228">236</span><span class="sxs-lookup"><span data-stu-id="89763-228">236</span></span>|

<span data-ttu-id="89763-229"><sup>\*</sup> 現在、この値は常に 0 です。</span><span class="sxs-lookup"><span data-stu-id="89763-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="89763-230">PermissionToViewHeader の場合、値 0 は検疫済みメッセージの詳細に [メッセージ ヘッダーの表示] ボタンを非表示にできません (このボタンは常に使用可能です)。</span><span class="sxs-lookup"><span data-stu-id="89763-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="89763-231"><sup>\*\*</sup> これらの両方の値を 1 に設定しない。</span><span class="sxs-lookup"><span data-stu-id="89763-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="89763-232">一方を 1 に設定し、もう一方を 0 に設定するか、両方を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="89763-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="89763-233">この例では、前の表で説明したように、No アクセス許可を割り当てる新しい検疫タグ名 NoAccess を作成します。</span><span class="sxs-lookup"><span data-stu-id="89763-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="89763-234">制限付きアクセス許可の場合は、値 106 を使用します。</span><span class="sxs-lookup"><span data-stu-id="89763-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="89763-235">フル アクセス許可の場合は、値 236 を使用します。</span><span class="sxs-lookup"><span data-stu-id="89763-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="89763-236">カスタム アクセス許可の場合は、前の表を使用して、必要なアクセス許可に対応するバイナリ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="89763-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="89763-237">2 進数の値を 10 進数の値に変換し _、EndUserQuarantinePermissionsValue パラメーターに 10 進値を使用_ します。</span><span class="sxs-lookup"><span data-stu-id="89763-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="89763-238">構文およびパラメーターの詳細については [、「New-QuarantineTag」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="89763-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="89763-239">EndUserQuarantinePermissions パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="89763-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="89763-240">_EndUserQuarantinePermissionsValue パラメーター_ を使用して検疫タグを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="89763-241">A.</span><span class="sxs-lookup"><span data-stu-id="89763-241">A.</span></span> <span data-ttu-id="89763-242">**New-QuarantinePermissions** コマンドレットを使用して、変数に検疫アクセス許可オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="89763-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="89763-243">B.</span><span class="sxs-lookup"><span data-stu-id="89763-243">B.</span></span> <span data-ttu-id="89763-244">変数を **New-QuarantineTag** コマンドの _EndUserQuarantinePermissions_ 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="89763-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="89763-245">手順 A: 検疫のアクセス許可オブジェクトを変数に格納する</span><span class="sxs-lookup"><span data-stu-id="89763-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="89763-246">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="89763-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="89763-247">使用されていないパラメーターの既定値は次の値なので、値を設定するパラメーターのみを `$false` 使用する必要があります `$true` 。</span><span class="sxs-lookup"><span data-stu-id="89763-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="89763-248">次の例は、事前設定されたアクセス許可グループに対応するアクセス許可オブジェクトを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="89763-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="89763-249">**アクセスなし**:</span><span class="sxs-lookup"><span data-stu-id="89763-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="89763-250">**制限付きアクセス**:</span><span class="sxs-lookup"><span data-stu-id="89763-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="89763-251">**フル アクセス**:</span><span class="sxs-lookup"><span data-stu-id="89763-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="89763-252">設定した値を確認するには、変数名をコマンドとして実行します (たとえば、コマンドを実行します `$NoAccess` )。</span><span class="sxs-lookup"><span data-stu-id="89763-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="89763-253">カスタム アクセス許可の場合は _、PermissionToRelease_ パラメーターと _PermissionToRequestRelease_ パラメーターの両方を次に設定してください `$true` 。</span><span class="sxs-lookup"><span data-stu-id="89763-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="89763-254">一方を設定 `$true` し、もう一方を次のように設定するか `$false` 、両方を次のようにします `$false` 。</span><span class="sxs-lookup"><span data-stu-id="89763-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="89763-255">また **、Set-QuarantinePermissions** コマンドレットを使用して、作成した後で使用する前に、既存のアクセス許可オブジェクト変数を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="89763-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="89763-256">構文およびパラメーターの詳細については [、「New-QuarantinePermissions」](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) および [「Set-QuarantinePermissions」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)。</span><span class="sxs-lookup"><span data-stu-id="89763-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="89763-257">手順 B: 次のコマンドで変数をNew-QuarantineTagする</span><span class="sxs-lookup"><span data-stu-id="89763-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="89763-258">アクセス許可オブジェクトを作成して変数に格納したら、次の **New-QuarantineTag** コマンドで _EndUserQuarantinePermission_ パラメーター値の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="89763-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="89763-259">この例では、前の手順で説明および作成したアクセス許可オブジェクトを使用して、LimitedAccess という名前の新しい検疫 `$LimitedAccess` タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="89763-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="89763-260">構文およびパラメーターの詳細については [、「New-QuarantineTag」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="89763-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="89763-261">手順 2: サポートされている機能に検疫タグを割り当てる</span><span class="sxs-lookup"><span data-stu-id="89763-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="89763-262">メッセージ _またはファイルを_ 検疫するサポートされる保護機能 (自動的に、または構成可能なアクションとして) では、使用可能な検疫アクションに検疫タグを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="89763-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="89763-263">次の表に、メッセージを検疫する機能と検疫タグの可用性について説明します。</span><span class="sxs-lookup"><span data-stu-id="89763-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="89763-264">機能</span><span class="sxs-lookup"><span data-stu-id="89763-264">Feature</span></span>|<span data-ttu-id="89763-265">サポートされている検疫タグ</span><span class="sxs-lookup"><span data-stu-id="89763-265">Quarantine tags supported?</span></span>|<span data-ttu-id="89763-266">使用される既定の検疫タグ</span><span class="sxs-lookup"><span data-stu-id="89763-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="89763-267">[スパム対策ポリシー](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="89763-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="89763-268">**Spam** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="89763-269">**信頼度の高い** スパム (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="89763-270">**フィッシング メール** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="89763-271">**信頼度の高いフィッシングメール** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="89763-272">**バルク メール** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="89763-273">はい</span><span class="sxs-lookup"><span data-stu-id="89763-273">Yes</span></span>|<ul><li><span data-ttu-id="89763-274">DefaultSpamTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="89763-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="89763-275">DefaultHighConfSpamTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="89763-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="89763-276">DefaultPhishTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="89763-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="89763-277">DefaultHighConfPhishTag (アクセスなし)</span><span class="sxs-lookup"><span data-stu-id="89763-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="89763-278">DefaultBulkTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="89763-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="89763-279">フィッシング対策ポリシー:</span><span class="sxs-lookup"><span data-stu-id="89763-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="89763-280">[スプーフィング インテリジェンス保護](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="89763-281">[偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="89763-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="89763-282">**偽装されたユーザーによって電子メールが送信される場合** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="89763-283">**偽装ドメイン**_(TargetedDomainProtectionAction) によって電子メールが送信される場合_</span><span class="sxs-lookup"><span data-stu-id="89763-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="89763-284">**メールボックス インテリジェンス** \>**偽装されたユーザーによって電子メールが送信** される場合 (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="89763-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="89763-285">いいえ</span><span class="sxs-lookup"><span data-stu-id="89763-285">No</span></span>|<span data-ttu-id="89763-286">該当なし</span><span class="sxs-lookup"><span data-stu-id="89763-286">n/a</span></span>|
|<span data-ttu-id="89763-287">[マルウェア対策ポリシー](configure-anti-malware-policies.md): 検出されたメッセージはすべて常に検疫されます。</span><span class="sxs-lookup"><span data-stu-id="89763-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="89763-288">いいえ</span><span class="sxs-lookup"><span data-stu-id="89763-288">No</span></span>|<span data-ttu-id="89763-289">該当なし</span><span class="sxs-lookup"><span data-stu-id="89763-289">n/a</span></span>|
|[<span data-ttu-id="89763-290">SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="89763-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="89763-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="89763-291">No</span></span>|<span data-ttu-id="89763-292">該当なし</span><span class="sxs-lookup"><span data-stu-id="89763-292">n/a</span></span>|
|<span data-ttu-id="89763-293">[アクションを含む](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) メール フロー ルール (トランスポート ルールとも呼ばれる): ホストされた検疫 (検疫) にメッセージ **を** 配信 _します_。</span><span class="sxs-lookup"><span data-stu-id="89763-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="89763-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="89763-294">No</span></span>|<span data-ttu-id="89763-295">該当なし</span><span class="sxs-lookup"><span data-stu-id="89763-295">n/a</span></span>|
|

<span data-ttu-id="89763-296"><sup>\*</sup> 偽装保護の設定は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="89763-297">既定の検疫タグによって提供されるエンド ユーザーのアクセス許可に満足している場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89763-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="89763-298">エンド ユーザーのスパム通知または検疫済みメッセージの詳細でエンド ユーザーの機能 (使用可能なボタン) をカスタマイズする場合は、カスタム検疫タグを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="89763-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="89763-299">セキュリティ/コンプライアンス センターでスパム対策ポリシーに検疫タグ&割り当てる</span><span class="sxs-lookup"><span data-stu-id="89763-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="89763-300">スパム対策ポリシーを作成および変更するための詳細な手順については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="89763-301">セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、[スパム対策] \>  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89763-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="89763-302">または、開きます <https://protection.office.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="89763-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="89763-303">既存のスパム対策ポリシーを検索して選択し、編集するか、新しいスパム対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="89763-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="89763-304">ポリシーの詳細のフライアウトで、[スパムと一括アクション **] セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="89763-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="89763-305">利用可能なスパム フィルターの条件のアクションに対して [検疫メッセージ] を選択した場合は、[検疫ポリシーの適用] タグ ボックスを使用して、その条件の検疫タグを選択できます。</span><span class="sxs-lookup"><span data-stu-id="89763-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="89763-306">**注**: 新しいポリシーを作成すると、スパム フィルターの条件に対して空白の検疫タグ値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89763-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="89763-307">後でポリシーを編集すると、前の表で説明したように、空白値が実際の既定の検疫タグ名に置き換えられる。</span><span class="sxs-lookup"><span data-stu-id="89763-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![スパム対策ポリシーでの検疫タグの選択](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="89763-309">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89763-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="89763-310">PowerShell でスパム対策ポリシーで検疫タグを割り当てる</span><span class="sxs-lookup"><span data-stu-id="89763-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="89763-311">スパム対策ポリシーで検疫タグを割り当てるには、PowerShell を使用する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89763-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="89763-312">**注**:</span><span class="sxs-lookup"><span data-stu-id="89763-312">**Notes**:</span></span>

- <span data-ttu-id="89763-313">_HighConfidencePhishAction_ パラメーターの既定値は Quarantine なので、新しいスパム対策ポリシーで信頼度の高いフィッシング検出の検疫アクションを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89763-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="89763-314">新規または既存のスパム対策ポリシーの他のすべてのスパム フィルターの条件では、検疫タグはアクションの値が Quarantine の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="89763-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="89763-315">既存のスパム対策ポリシーのアクション値を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="89763-316">Standard および Strict の既定のアクション値と推奨されるアクション値の詳細については、「EOP スパム対策ポリシー設定」 [を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="89763-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="89763-317">対応する検疫タグ パラメーターを指定しないスパム フィルターの条件は[](#step-2-assign-a-quarantine-tag-to-supported-features)、その確認の既定の検疫タグが使用されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="89763-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="89763-318">既定の検疫タグをカスタム検疫タグに置き換える必要があるのは、検疫済みメッセージの既定のエンド ユーザー機能を変更する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="89763-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="89763-319">PowerShell の新しいスパム対策ポリシーには **、New-HostedContentFilterPolicy** コマンドレットを使用するスパム フィルター ポリシー (設定) と **、New-HostedContentFilterRule** コマンドレットを使用する新しいスパム フィルター ルール (受信者フィルター) が必要です。</span><span class="sxs-lookup"><span data-stu-id="89763-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="89763-320">手順については [、「PowerShell を使用してスパム対策ポリシーを作成する」を参照してください](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="89763-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="89763-321">この例では、次の設定で Research Department という名前の新しいスパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="89763-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="89763-322">すべてのスパム フィルターの条件に対するアクションが [検疫] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="89763-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="89763-323">アクセス許可なしを割り当てる NoAccess という名前のカスタム検疫タグは、既定でアクセス許可を割り当てない既定の検疫タグに置き換わります。 </span><span class="sxs-lookup"><span data-stu-id="89763-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="89763-324">構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="89763-325">この例では、Human Resources という名前の既存のスパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="89763-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="89763-326">スパム検疫の確認のアクションは [検疫] に設定され、NoAccess という名前のカスタム検疫タグが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="89763-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="89763-327">構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="89763-328">セキュリティ/コンプライアンス センターでグローバル検疫通知&構成する</span><span class="sxs-lookup"><span data-stu-id="89763-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="89763-329">検疫タグのグローバル設定を使用すると、検疫されたメッセージの受信者に送信されるエンドユーザーのスパム通知をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="89763-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="89763-330">これらの通知の詳細については、「エンド ユーザー向け [スパム通知」を参照してください](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="89763-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="89763-331">セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="89763-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="89763-332">[検疫タグ **] ページで、[** グローバル設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89763-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="89763-333">開く **検疫通知設定** のフライアウトで、次の設定の一部またはすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="89763-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="89763-334">**会社のロゴを使用** する : エンド ユーザーのスパム通知の上部で使用されている既定の Microsoft ロゴを置き換える場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="89763-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="89763-335">これを行う前に、「組織の [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) テーマをカスタマイズする」の手順に従って、カスタム ロゴをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89763-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="89763-336">次のスクリーンショットは、エンド ユーザーのスパム通知のカスタム ロゴを示しています。</span><span class="sxs-lookup"><span data-stu-id="89763-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![エンドユーザーのスパム通知のカスタム ロゴ](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="89763-338">**[言語の** 選択]: エンドユーザーのスパム通知は、受信者の言語設定に基づいて既にローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="89763-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="89763-339">表示名と免責事項の値には、異なる言語 **でカスタマイズしたテキスト** を **指定** できます。</span><span class="sxs-lookup"><span data-stu-id="89763-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="89763-340">最初の言語ボックスから少なくとも 1 つの言語を選択し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="89763-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="89763-341">複数の言語を選択するには、各言語の後にある [追加 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89763-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="89763-342">セクションの言語ボックスには、選択した言語すべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89763-342">A section language box shows all of the languages that you've selected:</span></span>

     ![検疫タグのグローバル検疫通知設定の 2 番目の言語ボックスで選択した言語](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="89763-344">**表示名**: エンドユーザーのスパム通知で使用される送信者の表示名をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="89763-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="89763-345">追加した言語ごとに、2 番目の言語のボックス ([X] をクリックしない) で言語を選択し、[表示名] ボックスに目的のテキスト値 **を** 入力します。</span><span class="sxs-lookup"><span data-stu-id="89763-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="89763-346">次のスクリーンショットは、エンド ユーザーのスパム通知のカスタマイズされた表示名を示しています。</span><span class="sxs-lookup"><span data-stu-id="89763-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![エンド ユーザーのスパム通知でのカスタマイズされた送信者の表示名](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="89763-348">**免責** 事項 : エンドユーザーのスパム通知の下部にカスタム免責事項を追加します。</span><span class="sxs-lookup"><span data-stu-id="89763-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="89763-349">ローカライズされたテキスト、組織からの免責事項 **:** 常に最初に含め、その後に指定したテキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="89763-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="89763-350">追加した言語ごとに、2 番目の言語ボックス ([X] をクリックしない) で言語を選択し、必要なテキスト値を [免責事項] ボックスに **入力** します。</span><span class="sxs-lookup"><span data-stu-id="89763-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="89763-351">次のスクリーンショットは、エンド ユーザーのスパム通知でカスタマイズされた免責事項を示しています。</span><span class="sxs-lookup"><span data-stu-id="89763-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![エンドユーザーのスパム通知の下部にあるカスタム免責事項](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="89763-353">セキュリティ/コンプライアンス センターで検疫タグ&表示する</span><span class="sxs-lookup"><span data-stu-id="89763-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="89763-354">セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="89763-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="89763-355">組み込みまたはカスタム検疫タグの設定を表示するには、一覧から検疫タグを選択します (チェック ボックスはオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="89763-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="89763-356">グローバル設定を表示するには、[グローバル設定] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="89763-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="89763-357">PowerShell で検疫タグを表示する</span><span class="sxs-lookup"><span data-stu-id="89763-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="89763-358">PowerShell を使用して検疫タグを表示する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="89763-359">すべての組み込みタグまたはカスタム タグの要約リストを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="89763-360">組み込みまたはカスタム検疫タグの設定を表示するには、検疫タグの名前に置き換え、次の \<TagName\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="89763-361">グローバル設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="89763-362">構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="89763-363">セキュリティ/コンプライアンス センターで検疫&を削除する</span><span class="sxs-lookup"><span data-stu-id="89763-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="89763-364">**注**:</span><span class="sxs-lookup"><span data-stu-id="89763-364">**Notes**:</span></span>

- <span data-ttu-id="89763-365">組み込みの検疫タグは削除できない。</span><span class="sxs-lookup"><span data-stu-id="89763-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="89763-366">カスタム検疫タグを削除する前に、そのタグが使用されていないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="89763-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="89763-367">たとえば、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="89763-368">検疫タグが使用されている場合は、割り当てられた [検疫タグを](#step-2-assign-a-quarantine-tag-to-supported-features) 削除する前に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="89763-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="89763-369">セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="89763-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="89763-370">[検疫タグ **] ページ** で、削除するカスタム検疫タグを選択し、[削除] タグを **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="89763-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="89763-371">表示 **される確認ダイアログ** で [タグの削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89763-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="89763-372">PowerShell で検疫タグを削除する</span><span class="sxs-lookup"><span data-stu-id="89763-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="89763-373">PowerShell を使用してカスタム検疫タグを削除する場合は、検疫タグの名前に置き換え、次の \<TagName\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89763-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="89763-374">構文およびパラメーターの詳細については [、「Remove-QuarantineTag」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="89763-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="89763-375">検疫タグのアクセス許可の詳細</span><span class="sxs-lookup"><span data-stu-id="89763-375">Quarantine tag permission details</span></span>

<span data-ttu-id="89763-376">以下のセクションでは、検疫済みメッセージの詳細およびエンド ユーザーのスパム通知における、事前設定されたアクセス許可グループと個々のアクセス許可の影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="89763-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="89763-377">事前に設定されたアクセス許可グループ</span><span class="sxs-lookup"><span data-stu-id="89763-377">Preset permissions groups</span></span>

<span data-ttu-id="89763-378">既定のアクセス許可グループに含まれる個々のアクセス許可を、この記事の冒頭の表に示します。</span><span class="sxs-lookup"><span data-stu-id="89763-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="89763-379">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="89763-379">No access</span></span>

<span data-ttu-id="89763-380">検疫タグでアクセス許可なし(アクセス許可なし) が割り当てらた場合でも、ユーザーには次のベースライン機能があります。</span><span class="sxs-lookup"><span data-stu-id="89763-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="89763-381">**検疫済みメッセージの詳細**: [ **メッセージ ヘッダーの表示]** ボタンは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![検疫タグがユーザーにアクセス許可を与えがない場合に、検疫済みメッセージの詳細に表示される使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="89763-383">**エンドユーザーのスパム通知**: 検疫 **内** のメッセージにユーザーを移動する [レビュー] ボタンは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![検疫タグがユーザーにアクセス許可を与えがない場合に、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="89763-385">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89763-385">Limited access</span></span>

<span data-ttu-id="89763-386">検疫タグが制限付きアクセス許可を **割り当** てると、ユーザーは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="89763-387">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="89763-388">**リリースを要求する**</span><span class="sxs-lookup"><span data-stu-id="89763-388">**Request release**</span></span>
  - <span data-ttu-id="89763-389">**メッセージ ヘッダーの表示**</span><span class="sxs-lookup"><span data-stu-id="89763-389">**View message header**</span></span>
  - <span data-ttu-id="89763-390">**プレビュー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="89763-390">**Preview message**</span></span>
  - <span data-ttu-id="89763-391">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="89763-391">**Block sender**</span></span>
  - <span data-ttu-id="89763-392">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="89763-392">**Remove from quarantine**</span></span>

  ![検疫タグがユーザーに制限付きアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="89763-394">**エンド ユーザーのスパム通知**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="89763-395">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="89763-395">**Block sender**</span></span>
  - <span data-ttu-id="89763-396">**確認**</span><span class="sxs-lookup"><span data-stu-id="89763-396">**Review**</span></span>

  ![検疫タグがユーザーに制限付きアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="89763-398">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="89763-398">Full access</span></span>

<span data-ttu-id="89763-399">検疫タグがフル アクセスの **アクセス許可** (使用可能なすべてのアクセス許可) を割り当てると、ユーザーは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="89763-400">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="89763-401">**メッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="89763-401">**Release message**</span></span>
  - <span data-ttu-id="89763-402">**メッセージ ヘッダーの表示**</span><span class="sxs-lookup"><span data-stu-id="89763-402">**View message header**</span></span>
  - <span data-ttu-id="89763-403">**プレビュー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="89763-403">**Preview message**</span></span>
  - <span data-ttu-id="89763-404">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="89763-404">**Block sender**</span></span>
  - <span data-ttu-id="89763-405">**送信者を許可する**</span><span class="sxs-lookup"><span data-stu-id="89763-405">**Allow sender**</span></span>
  - <span data-ttu-id="89763-406">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="89763-406">**Remove from quarantine**</span></span>

  ![検疫タグがユーザーにフル アクセスのアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="89763-408">**エンド ユーザーのスパム通知**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="89763-409">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="89763-409">**Block sender**</span></span>
  - <span data-ttu-id="89763-410">**リリース**</span><span class="sxs-lookup"><span data-stu-id="89763-410">**Release**</span></span>
  - <span data-ttu-id="89763-411">**確認**</span><span class="sxs-lookup"><span data-stu-id="89763-411">**Review**</span></span>

  ![検疫タグがユーザーにフル アクセスのアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="89763-413">個々のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="89763-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="89763-414">ユーザーには、常に「アクセスなし」セクションで説明されている [ボタンが表示](#no-access) されます。</span><span class="sxs-lookup"><span data-stu-id="89763-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="89763-415">これらのボタンは、個々のアクセス許可の説明には含まれません。</span><span class="sxs-lookup"><span data-stu-id="89763-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="89763-416">送信者のアクセス許可を許可する</span><span class="sxs-lookup"><span data-stu-id="89763-416">Allow sender permission</span></span>

<span data-ttu-id="89763-417">送信者 **の許可**_(PermissionToAllowSender)_ は、検疫済みメッセージの送信者を安全な差出人のリストに簡単に追加できるボタンへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="89763-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="89763-418">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="89763-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="89763-419">**[送信者のアクセス許可** を有効にする]: [送信者 **を許可する]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="89763-420">**[送信者のアクセス** 許可を無効にする]: [送信者 **を許可する]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="89763-421">**エンドユーザーのスパム通知**: 効果なし。</span><span class="sxs-lookup"><span data-stu-id="89763-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="89763-422">差出人セーフ リストの詳細については、「信頼[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)できる差出人がブロックされるのを防ぐ」および[「Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスのセーフリスト コレクションを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="89763-423">送信者のアクセス許可をブロックする</span><span class="sxs-lookup"><span data-stu-id="89763-423">Block sender permission</span></span>

<span data-ttu-id="89763-424">送信者 **のブロック** のアクセス許可 _(PermissionToBlockSender)_ は、ユーザーが検疫済みメッセージの送信者を受信拒否リストに簡単に追加できるボタンへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="89763-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="89763-425">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="89763-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="89763-426">**[送信者のアクセス** 許可をブロックする] を有効にする: [送信者 **のブロック]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="89763-427">**[送信者のアクセス** 許可をブロックする] が無効になっている: [送信者 **のブロック]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="89763-428">**エンドユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="89763-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="89763-429">**[送信者のアクセス** 許可をブロックする] が無効になっている: [送信者 **のブロック]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="89763-430">**[送信者のアクセス** 許可をブロックする] を有効にする: [送信者 **のブロック]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="89763-431">受信拒否リストの詳細については、「他のユーザーからのメッセージ[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)をブロックする」および[「Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスのセーフリスト コレクションを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89763-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="89763-432">削除のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="89763-432">Delete permission</span></span>

<span data-ttu-id="89763-433">削除 **アクセス** 許可 (_PermissionToDelete_) は、ユーザーが検疫からメッセージ (ユーザーが受信者であるメッセージ) を削除する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="89763-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="89763-434">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="89763-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="89763-435">**削除** のアクセス許可が有効になっている: [ **検疫から削除]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="89763-436">**削除** のアクセス許可が無効になっている: [ **検疫から削除]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="89763-437">**エンドユーザーのスパム通知**: 効果なし。</span><span class="sxs-lookup"><span data-stu-id="89763-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="89763-438">プレビューのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="89763-438">Preview permission</span></span>

<span data-ttu-id="89763-439">プレビュー **の** アクセス許可 _(PermissionToPreview)_ は、ユーザーが検疫でメッセージをプレビューする機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="89763-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="89763-440">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="89763-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="89763-441">**プレビュー** のアクセス許可の有効化: **[メッセージのプレビュー]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="89763-442">**プレビュー** のアクセス許可が無効になっている: **[メッセージのプレビュー]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="89763-443">**エンドユーザーのスパム通知**: 効果なし。</span><span class="sxs-lookup"><span data-stu-id="89763-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="89763-444">受信者に検疫のアクセス許可からのメッセージの解放を許可する</span><span class="sxs-lookup"><span data-stu-id="89763-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="89763-445">受信者 **が** 検疫のアクセス許可 _(PermissionToRelease)_ からメッセージを解放する許可は、ユーザーが検疫済みメッセージを管理者の承認なしに直接解放する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="89763-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="89763-446">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="89763-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="89763-447">アクセス許可の有効化: **[メッセージの解放]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="89763-448">アクセス許可が無効: **[メッセージの解放]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="89763-449">**エンドユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="89763-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="89763-450">アクセス許可の有効化: **[リリース]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="89763-451">アクセス許可が無効: **[リリース** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="89763-452">受信者が検疫のアクセス許可から解放されるメッセージを要求する</span><span class="sxs-lookup"><span data-stu-id="89763-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="89763-453">[**受信者に** 検疫からのメッセージの解放を要求する] アクセス許可 _(PermissionToRequestRelease)_ は、ユーザーが検疫済みメッセージの解放を要求する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="89763-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="89763-454">メッセージは、管理者が要求を承認した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="89763-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="89763-455">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="89763-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="89763-456">アクセス許可の有効化: **[要求] リリース** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89763-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="89763-457">アクセス許可が無効: **[要求] リリース** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="89763-458">**エンドユーザーのスパム通知**: [ **リリース]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89763-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
