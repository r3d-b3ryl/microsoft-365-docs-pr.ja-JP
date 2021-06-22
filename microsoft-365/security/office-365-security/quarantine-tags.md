---
title: 検疫ポリシー
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
description: 管理者は、検疫ポリシーを使用して、検疫されたメッセージに対してユーザーが実行できる操作を制御する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055202"
---
# <a name="quarantine-policies"></a><span data-ttu-id="54d16-103">検疫ポリシー</span><span class="sxs-lookup"><span data-stu-id="54d16-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="54d16-104">この記事で説明する機能は、現在プレビュー中であり、すべてのユーザーが利用できる機能ではなく、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54d16-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="54d16-105">Exchange Online Protection (EOP) の検疫ポリシー (以前は検疫タグと呼ばれる) を使用すると、管理者は、メッセージが検疫に到着した方法に基づいて、検疫されたメッセージに対してユーザーが実行できる操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="54d16-106">EOP は、従来、検疫およびエンド ユーザーのスパム通知のメッセージに[](find-and-release-quarantined-messages-as-a-user.md)対して、特定のレベルの対話機能を許可または[防止しています](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="54d16-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="54d16-107">たとえば、ユーザーはスパム対策フィルターによって検疫されたメッセージをスパムまたは一括として表示および解放できますが、高信頼フィッシングとして検疫されたメッセージを表示または解放できない (管理者だけが実行できます)。</span><span class="sxs-lookup"><span data-stu-id="54d16-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="54d16-108">サポート [されている保護機能](#step-2-assign-a-quarantine-policy-to-supported-features)の場合、検疫ポリシーは、エンドユーザーのスパム通知メッセージと検疫中の検疫済みメッセージ (ユーザーが受信者であるメッセージ) でユーザーが実行できる操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="54d16-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="54d16-109">既定の検疫ポリシーは、検疫されたメッセージに対してユーザーの履歴機能を適用するために自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="54d16-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="54d16-110">または、カスタム検疫ポリシーを作成して割り当て、エンド ユーザーが検疫済みメッセージに対して特定のアクションを実行を許可または防止できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="54d16-111">個々のアクセス許可は、次の事前設定されたアクセス許可グループに組み合わされます。</span><span class="sxs-lookup"><span data-stu-id="54d16-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="54d16-112">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="54d16-112">No access</span></span>
- <span data-ttu-id="54d16-113">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-113">Limited access</span></span>
- <span data-ttu-id="54d16-114">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-114">Full access</span></span>

<span data-ttu-id="54d16-115">使用可能な個々のアクセス許可と、事前設定されたアクセス許可グループに含まれているか含まれていないかについて、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="54d16-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="54d16-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="54d16-116">Permission</span></span>|<span data-ttu-id="54d16-117">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="54d16-117">No access</span></span>|<span data-ttu-id="54d16-118">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-118">Limited access</span></span>|<span data-ttu-id="54d16-119">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="54d16-120">**送信者を許可** する (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="54d16-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="54d16-122">**送信者のブロック** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="54d16-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="54d16-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="54d16-125">**Delete** (_PermissionToDelete_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="54d16-128">**プレビュー** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="54d16-128">**Preview** (_PermissionToPreview_)</span></span>||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="54d16-131">**受信者に検疫からのメッセージの解放を許可** する (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="54d16-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![チェック マーク](../../media/checkmark.png)|
|<span data-ttu-id="54d16-133">**受信者がメッセージを検疫から** 解放する要求を許可する (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="54d16-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![チェック マーク](../../media/checkmark.png)||
|

<span data-ttu-id="54d16-135">事前設定されたアクセス許可グループの既定のアクセス許可が気に入らない場合は、カスタム検疫ポリシーを作成または変更するときにカスタムアクセス許可を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="54d16-136">各アクセス許可の動作の詳細については、この記事の後半の「 [検疫ポリシーのアクセス許可の詳細](#quarantine-policy-permission-details) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="54d16-137">Microsoft 365 Defender ポータルまたは PowerShell で検疫ポリシーを作成および割り当てる (Exchange Online メールボックスを持つ Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない EOP 組織ではスタンドアロンの EOP PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="54d16-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="54d16-138">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="54d16-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="54d16-139"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="54d16-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="54d16-140">または、[検疫ポリシー] ページに直接 **移動するには、** を開きます <https://security.microsoft.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="54d16-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="54d16-141">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="54d16-142">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="54d16-143">検疫ポリシーを表示、Microsoft 365 Defender 作成、変更、または削除するには、組織の管理またはセキュリティ管理者の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="54d16-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="54d16-144">詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="54d16-145">手順 1: セキュリティ ポータルで検疫ポリシーをMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="54d16-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="54d16-146">[セキュリティ ポータルMicrosoft 365 Defenderに移動し、[電子メール &**の** 脅威ポリシー] セクションの [検疫ポリシー] に移動し、[検疫ポリシー \>  \>  \>  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54d16-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="54d16-147">[検疫ポリシー **] ページで** 、[カスタム ポリシーの追加] アイコン [カスタム ![ ](../../media/m365-cc-sc-create-icon.png) **ポリシーの追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="54d16-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="54d16-148">新 **しいポリシー ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="54d16-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="54d16-149">[ポリシー名 **] ページで** 、[ポリシー名] ボックスに簡単な一意の **名前を入力** します。</span><span class="sxs-lookup"><span data-stu-id="54d16-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="54d16-150">今後の手順では、名前で検疫ポリシーを識別して選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54d16-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="54d16-151">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d16-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="54d16-152">[受信者メッセージ **アクセス] ページ** で、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="54d16-153">**アクセスなし**</span><span class="sxs-lookup"><span data-stu-id="54d16-153">**No access**</span></span>
   - <span data-ttu-id="54d16-154">**制限付きアクセス**</span><span class="sxs-lookup"><span data-stu-id="54d16-154">**Limited access**</span></span>
   - <span data-ttu-id="54d16-155">**フル アクセス**</span><span class="sxs-lookup"><span data-stu-id="54d16-155">**Full access**</span></span>

   <span data-ttu-id="54d16-156">これらのアクセス許可グループに含まれる個々のアクセス許可については、この記事の前で説明します。</span><span class="sxs-lookup"><span data-stu-id="54d16-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="54d16-157">カスタムアクセス許可を指定するには、[特定のアクセス **許可を設定する (Advanced)** を選択し、表示される次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="54d16-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="54d16-158">**[リリース アクションの基本設定]** を選択します。次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="54d16-159">**リリースアクションなし**: これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="54d16-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="54d16-160">**受信者が検疫からメッセージを解放するを許可する**</span><span class="sxs-lookup"><span data-stu-id="54d16-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="54d16-161">**受信者が検疫からメッセージを解放する要求を許可する**</span><span class="sxs-lookup"><span data-stu-id="54d16-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="54d16-162">**検疫済みメッセージに対して** 受信者が実行できる追加のアクションを選択する: 次の値の一部、すべて、またはなしを選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="54d16-163">**削除**</span><span class="sxs-lookup"><span data-stu-id="54d16-163">**Delete**</span></span>
       - <span data-ttu-id="54d16-164">**プレビュー**</span><span class="sxs-lookup"><span data-stu-id="54d16-164">**Preview**</span></span>
       - <span data-ttu-id="54d16-165">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="54d16-165">**Block sender**</span></span>

   <span data-ttu-id="54d16-166">これらのアクセス許可と検疫済みメッセージおよびエンド ユーザースパム通知への影響については、この記事の[](#quarantine-policy-permission-details)後半の「検疫ポリシーのアクセス許可の詳細」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="54d16-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="54d16-167">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d16-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="54d16-168">表示される **[ポリシーの確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="54d16-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="54d16-169">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="54d16-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="54d16-170">または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="54d16-171">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="54d16-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="54d16-172">表示された [確認]ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d16-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="54d16-173">これで、手順 2 の説明に従って検疫ポリシーを検疫機能に割 [り当てる準備ができました](#step-2-assign-a-quarantine-policy-to-supported-features) 。</span><span class="sxs-lookup"><span data-stu-id="54d16-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="54d16-174">PowerShell で検疫ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="54d16-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="54d16-175">PowerShell を使用して検疫ポリシーを作成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し **、New-QuarantineTag コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="54d16-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="54d16-176">次の 2 つの方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="54d16-177">_EndUserQuarantinePermissionsValue パラメーターを使用_ します。</span><span class="sxs-lookup"><span data-stu-id="54d16-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="54d16-178">_EndUserQuarantinePermissions パラメーターを使用_ します。</span><span class="sxs-lookup"><span data-stu-id="54d16-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="54d16-179">これらのメソッドについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="54d16-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="54d16-180">EndUserQuarantinePermissionsValue パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="54d16-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="54d16-181">_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="54d16-182">_EndUserQuarantinePermissionsValue_ パラメーターは、バイナリ値から変換される 10 進値を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="54d16-183">バイナリ値は、特定の順序で使用可能なエンド ユーザー検疫のアクセス許可に対応します。</span><span class="sxs-lookup"><span data-stu-id="54d16-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="54d16-184">アクセス許可ごとに、値 1 は True、値 0 は False に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="54d16-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="54d16-185">事前設定されたアクセス許可グループの各アクセス許可に必要な順序と値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="54d16-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="54d16-186">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="54d16-186">Permission</span></span>|<span data-ttu-id="54d16-187">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="54d16-187">No access</span></span>|<span data-ttu-id="54d16-188">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-188">Limited access</span></span>|<span data-ttu-id="54d16-189">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="54d16-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="54d16-190">PermissionToAllowSender</span></span>|<span data-ttu-id="54d16-191">0</span><span class="sxs-lookup"><span data-stu-id="54d16-191">0</span></span>|<span data-ttu-id="54d16-192">0</span><span class="sxs-lookup"><span data-stu-id="54d16-192">0</span></span>|<span data-ttu-id="54d16-193">1</span><span class="sxs-lookup"><span data-stu-id="54d16-193">1</span></span>|
|<span data-ttu-id="54d16-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="54d16-194">PermissionToBlockSender</span></span>|<span data-ttu-id="54d16-195">0</span><span class="sxs-lookup"><span data-stu-id="54d16-195">0</span></span>|<span data-ttu-id="54d16-196">1</span><span class="sxs-lookup"><span data-stu-id="54d16-196">1</span></span>|<span data-ttu-id="54d16-197">1</span><span class="sxs-lookup"><span data-stu-id="54d16-197">1</span></span>|
|<span data-ttu-id="54d16-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="54d16-198">PermissionToDelete</span></span>|<span data-ttu-id="54d16-199">0</span><span class="sxs-lookup"><span data-stu-id="54d16-199">0</span></span>|<span data-ttu-id="54d16-200">1</span><span class="sxs-lookup"><span data-stu-id="54d16-200">1</span></span>|<span data-ttu-id="54d16-201">1</span><span class="sxs-lookup"><span data-stu-id="54d16-201">1</span></span>|
|<span data-ttu-id="54d16-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54d16-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="54d16-203">0</span><span class="sxs-lookup"><span data-stu-id="54d16-203">0</span></span>|<span data-ttu-id="54d16-204">0</span><span class="sxs-lookup"><span data-stu-id="54d16-204">0</span></span>|<span data-ttu-id="54d16-205">0</span><span class="sxs-lookup"><span data-stu-id="54d16-205">0</span></span>|
|<span data-ttu-id="54d16-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="54d16-206">PermissionToPreview</span></span>|<span data-ttu-id="54d16-207">0</span><span class="sxs-lookup"><span data-stu-id="54d16-207">0</span></span>|<span data-ttu-id="54d16-208">1</span><span class="sxs-lookup"><span data-stu-id="54d16-208">1</span></span>|<span data-ttu-id="54d16-209">1</span><span class="sxs-lookup"><span data-stu-id="54d16-209">1</span></span>|
|<span data-ttu-id="54d16-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="54d16-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="54d16-211">0</span><span class="sxs-lookup"><span data-stu-id="54d16-211">0</span></span>|<span data-ttu-id="54d16-212">0</span><span class="sxs-lookup"><span data-stu-id="54d16-212">0</span></span>|<span data-ttu-id="54d16-213">1</span><span class="sxs-lookup"><span data-stu-id="54d16-213">1</span></span>|
|<span data-ttu-id="54d16-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="54d16-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="54d16-215">0</span><span class="sxs-lookup"><span data-stu-id="54d16-215">0</span></span>|<span data-ttu-id="54d16-216">1</span><span class="sxs-lookup"><span data-stu-id="54d16-216">1</span></span>|<span data-ttu-id="54d16-217">0</span><span class="sxs-lookup"><span data-stu-id="54d16-217">0</span></span>|
|<span data-ttu-id="54d16-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54d16-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="54d16-219">0</span><span class="sxs-lookup"><span data-stu-id="54d16-219">0</span></span>|<span data-ttu-id="54d16-220">0</span><span class="sxs-lookup"><span data-stu-id="54d16-220">0</span></span>|<span data-ttu-id="54d16-221">0</span><span class="sxs-lookup"><span data-stu-id="54d16-221">0</span></span>|
|<span data-ttu-id="54d16-222">バイナリ値</span><span class="sxs-lookup"><span data-stu-id="54d16-222">Binary value</span></span>|<span data-ttu-id="54d16-223">00000000</span><span class="sxs-lookup"><span data-stu-id="54d16-223">00000000</span></span>|<span data-ttu-id="54d16-224">01101010</span><span class="sxs-lookup"><span data-stu-id="54d16-224">01101010</span></span>|<span data-ttu-id="54d16-225">11101100</span><span class="sxs-lookup"><span data-stu-id="54d16-225">11101100</span></span>|
|<span data-ttu-id="54d16-226">使用する 10 進値</span><span class="sxs-lookup"><span data-stu-id="54d16-226">Decimal value to use</span></span>|<span data-ttu-id="54d16-227">0</span><span class="sxs-lookup"><span data-stu-id="54d16-227">0</span></span>|<span data-ttu-id="54d16-228">106</span><span class="sxs-lookup"><span data-stu-id="54d16-228">106</span></span>|<span data-ttu-id="54d16-229">236</span><span class="sxs-lookup"><span data-stu-id="54d16-229">236</span></span>|
|

<span data-ttu-id="54d16-230"><sup>\*</sup> 現在、この値は常に 0 です。</span><span class="sxs-lookup"><span data-stu-id="54d16-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="54d16-231">PermissionToViewHeader の場合、値 0 は検疫済みメッセージの詳細で [メッセージ ヘッダーの表示] ボタンを非表示にできません (ボタンは常に使用できます)。</span><span class="sxs-lookup"><span data-stu-id="54d16-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="54d16-232"><sup>\*\*</sup> 両方の値を 1 に設定しない。</span><span class="sxs-lookup"><span data-stu-id="54d16-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="54d16-233">1 を 1 に、もう一方を 0 に設定するか、両方を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="54d16-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="54d16-234">この例では、前の表で説明したように、アクセス許可なしを割り当てる新しい検疫ポリシー名 NoAccess を作成します。</span><span class="sxs-lookup"><span data-stu-id="54d16-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="54d16-235">制限付きアクセス許可の場合は、値 106 を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="54d16-236">[完全アクセス許可] の場合は、値 236 を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="54d16-237">カスタムアクセス許可の場合は、前の表を使用して、必要なアクセス許可に対応するバイナリ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="54d16-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="54d16-238">バイナリ値を 10 進値に変換し _、EndUserQuarantinePermissionsValue_ パラメーターに 10 進値を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="54d16-239">構文とパラメーターの詳細については [、「New-QuarantineTag」を参照してください](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="54d16-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="54d16-240">EndUserQuarantinePermissions パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="54d16-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="54d16-241">_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="54d16-242">A.</span><span class="sxs-lookup"><span data-stu-id="54d16-242">A.</span></span> <span data-ttu-id="54d16-243">**New-QuarantinePermissions** コマンドレットを使用して、検疫アクセス許可オブジェクトを変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="54d16-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="54d16-244">B.</span><span class="sxs-lookup"><span data-stu-id="54d16-244">B.</span></span> <span data-ttu-id="54d16-245">New-QuarantineTag コマンドの _EndUserQuarantinePermissions_ 値 **として変数を使用** します。</span><span class="sxs-lookup"><span data-stu-id="54d16-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="54d16-246">手順 A: 検疫アクセス許可オブジェクトを変数に格納する</span><span class="sxs-lookup"><span data-stu-id="54d16-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="54d16-247">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="54d16-248">未使用のパラメーターの既定値は次の値なので、値をに設定するパラメーターのみを `$false` 使用する必要があります `$true` 。</span><span class="sxs-lookup"><span data-stu-id="54d16-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="54d16-249">次の例は、事前設定されたアクセス許可グループに対応するアクセス許可オブジェクトを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54d16-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="54d16-250">**アクセスなし**:</span><span class="sxs-lookup"><span data-stu-id="54d16-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="54d16-251">**制限付きアクセス**:</span><span class="sxs-lookup"><span data-stu-id="54d16-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="54d16-252">**フル アクセス**:</span><span class="sxs-lookup"><span data-stu-id="54d16-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="54d16-253">設定した値を表示するには、変数名をコマンドとして実行します (たとえば、コマンドを実行します `$NoAccess` )。</span><span class="sxs-lookup"><span data-stu-id="54d16-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="54d16-254">カスタムアクセス許可の場合は _、PermissionToRelease_ パラメーターと _PermissionToRequestRelease_ パラメーターの両方をに設定しない `$true` 。</span><span class="sxs-lookup"><span data-stu-id="54d16-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="54d16-255">1 つを `$true` に設定し、もう一方を `$false` そのままにするか、両方をとして残します `$false` 。</span><span class="sxs-lookup"><span data-stu-id="54d16-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="54d16-256">作成後 **、Set-QuarantinePermissions** コマンドレットを使用して使用する前に、既存のアクセス許可オブジェクト変数を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="54d16-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="54d16-257">構文とパラメーターの詳細については [、「New-QuarantinePermissions」](/powershell/module/exchange/new-quarantinepermissions) および [「Set-QuarantinePermissions」を参照してください](/powershell/module/exchange/set-quarantinepermissions)。</span><span class="sxs-lookup"><span data-stu-id="54d16-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="54d16-258">手順 B: [変数] コマンドで変数New-QuarantineTagします。</span><span class="sxs-lookup"><span data-stu-id="54d16-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="54d16-259">permissions オブジェクトを変数に作成して格納したら、次の **New-QuarantineTag** コマンドで _EndUserQuarantinePermission_ パラメーター値の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="54d16-260">次の使用例は、前の手順で説明して作成したアクセス許可オブジェクトを使用して、LimitedAccess という名前の新しい検疫 `$LimitedAccess` ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54d16-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="54d16-261">構文とパラメーターの詳細については [、「New-QuarantineTag」を参照してください](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="54d16-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="54d16-262">手順 2: 検疫ポリシーをサポートされている機能に割り当てる</span><span class="sxs-lookup"><span data-stu-id="54d16-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="54d16-263">メッセージ _またはファイルを_ 検疫するサポートされている保護機能 (自動的に、または構成可能なアクションとして) では、検疫ポリシーを使用可能な検疫アクションに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="54d16-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="54d16-264">メッセージを検疫する機能と検疫ポリシーの可用性については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="54d16-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="54d16-265">機能</span><span class="sxs-lookup"><span data-stu-id="54d16-265">Feature</span></span>|<span data-ttu-id="54d16-266">検疫ポリシーがサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="54d16-266">Quarantine policies supported?</span></span>|<span data-ttu-id="54d16-267">使用される既定の検疫ポリシー</span><span class="sxs-lookup"><span data-stu-id="54d16-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="54d16-268">[スパム対策ポリシー](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="54d16-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="54d16-269">**スパム** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="54d16-270">**高信頼スパム** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="54d16-271">**フィッシング** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="54d16-272">**高信頼フィッシング** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="54d16-273">**Bulk** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="54d16-274">はい</span><span class="sxs-lookup"><span data-stu-id="54d16-274">Yes</span></span>|<ul><li><span data-ttu-id="54d16-275">DefaultSpamTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="54d16-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="54d16-276">DefaultHighConfSpamTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="54d16-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="54d16-277">DefaultPhishTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="54d16-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="54d16-278">DefaultHighConfPhishTag (アクセスなし)</span><span class="sxs-lookup"><span data-stu-id="54d16-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="54d16-279">DefaultBulkTag (フル アクセス)</span><span class="sxs-lookup"><span data-stu-id="54d16-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="54d16-280">フィッシング対策ポリシー:</span><span class="sxs-lookup"><span data-stu-id="54d16-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="54d16-281">[スプーフィング インテリジェンス保護](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="54d16-282">[偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54d16-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="54d16-283">**偽装ユーザーとしてメッセージが検出された場合** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="54d16-284">**偽装ドメインとしてメッセージが検出された場合** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="54d16-285">**メールボックス インテリジェンスがユーザーを検出して偽装した場合** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="54d16-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="54d16-286">いいえ</span><span class="sxs-lookup"><span data-stu-id="54d16-286">No</span></span>|<span data-ttu-id="54d16-287">該当なし</span><span class="sxs-lookup"><span data-stu-id="54d16-287">n/a</span></span>|
|<span data-ttu-id="54d16-288">[マルウェア対策ポリシー](configure-anti-malware-policies.md): 検出されたメッセージはすべて常に検疫されます。</span><span class="sxs-lookup"><span data-stu-id="54d16-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="54d16-289">いいえ</span><span class="sxs-lookup"><span data-stu-id="54d16-289">No</span></span>|<span data-ttu-id="54d16-290">該当なし</span><span class="sxs-lookup"><span data-stu-id="54d16-290">n/a</span></span>|
|[<span data-ttu-id="54d16-291">SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="54d16-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="54d16-292">いいえ</span><span class="sxs-lookup"><span data-stu-id="54d16-292">No</span></span>|<span data-ttu-id="54d16-293">該当なし</span><span class="sxs-lookup"><span data-stu-id="54d16-293">n/a</span></span>|
|<span data-ttu-id="54d16-294">[アクションを含む](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) メール フロー ルール (トランスポート ルールとも呼ばれる): メッセージをホストされた検疫 (検疫) **に** 配信 _します_。</span><span class="sxs-lookup"><span data-stu-id="54d16-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="54d16-295">いいえ</span><span class="sxs-lookup"><span data-stu-id="54d16-295">No</span></span>|<span data-ttu-id="54d16-296">該当なし</span><span class="sxs-lookup"><span data-stu-id="54d16-296">n/a</span></span>|
|

<span data-ttu-id="54d16-297"><sup>\*</sup>偽装保護の設定は、Microsoft Defender のフィッシング対策ポリシーでのみOffice 365。</span><span class="sxs-lookup"><span data-stu-id="54d16-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="54d16-298">既定の検疫ポリシーによって提供されるエンド ユーザーのアクセス許可に満足している場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="54d16-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="54d16-299">エンド ユーザーのスパム通知または検疫済みメッセージの詳細でエンド ユーザー機能 (使用可能なボタン) をカスタマイズする場合は、カスタム検疫ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="54d16-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="54d16-300">スパム対策ポリシーで検疫ポリシーを割り当てるには、Microsoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="54d16-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="54d16-301">スパム対策ポリシーを作成および変更する手順の詳細については、「EOP でのスパム対策ポリシーの構成」 [を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="54d16-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="54d16-302">[メール Microsoft 365 Defender] ポータルで、[メール &**ポリシー** ] &[スパム対策] \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="54d16-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="54d16-303">または、 を開きます <https://security.microsoft.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="54d16-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="54d16-304">[スパム **対策ポリシー] ページで** 、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="54d16-305">既存の受信スパム対策 **ポリシーを** 検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="54d16-306">新しい受信 **スパム対策** ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54d16-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="54d16-307">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="54d16-308">**既存のスパム対策ポリシーを** 編集する : ポリシーの詳細フライアウトで、[アクション] セクションに移動し、[アクションの編集]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="54d16-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="54d16-309">**新しいスパム対策ポリシーを作成する**: 新しいポリシー ウィザードで、[アクション] ページ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="54d16-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="54d16-310">[操作 **] ページ** で。</span><span class="sxs-lookup"><span data-stu-id="54d16-310">On the **Actions** page.</span></span> <span data-ttu-id="54d16-311">検疫メッセージ アクションを持つすべての評決には、対応する検疫ポリシーを選択する [検疫ポリシーの選択] ボックスも表示されます。</span><span class="sxs-lookup"><span data-stu-id="54d16-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="54d16-312">**注**: 新しいポリシーを作成する場合、空の **[** 検疫ポリシーの選択] の値は、その評決の既定の検疫ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="54d16-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="54d16-313">後でポリシーを編集すると、前の表で説明したように、空白の値が実際の既定の検疫ポリシー名に置き換えられる。</span><span class="sxs-lookup"><span data-stu-id="54d16-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![スパム対策ポリシーの検疫ポリシーの選択](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="54d16-315">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d16-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="54d16-316">PowerShell のスパム対策ポリシーで検疫ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="54d16-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="54d16-317">スパム対策ポリシーで検疫ポリシーを割り当てる場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="54d16-318">**注**:</span><span class="sxs-lookup"><span data-stu-id="54d16-318">**Notes**:</span></span>

- <span data-ttu-id="54d16-319">_HighConfidencePhishAction_ パラメーターの既定値は [検疫] なので、新しいスパム対策ポリシーで高信頼フィッシング検出の検疫アクションを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="54d16-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="54d16-320">新しいスパム対策ポリシーまたは既存のスパム対策ポリシーの他のすべてのスパム フィルターの評決では、検疫ポリシーは、アクション値が [検疫] の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="54d16-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="54d16-321">既存のスパム対策ポリシーのアクション値を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="54d16-322">Standard および Strict の既定のアクション値と推奨されるアクション値については、「EOP スパム対策ポリシー設定」 [を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="54d16-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="54d16-323">対応する検疫ポリシー パラメーターのないスパム フィルターの評決は、[](#step-2-assign-a-quarantine-policy-to-supported-features)その評決の既定の検疫ポリシーが使用されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="54d16-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="54d16-324">検疫済みメッセージの既定のエンド ユーザー機能を変更する場合は、既定の検疫ポリシーをカスタム検疫ポリシーに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="54d16-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="54d16-325">PowerShell の新しいスパム対策ポリシーには **、New-HostedContentFilterPolicy** コマンドレットを使用するスパム フィルター ポリシー (設定) と **、New-HostedContentFilterRule** コマンドレットを使用する新しいスパム フィルター ルール (受信者フィルター) が必要です。</span><span class="sxs-lookup"><span data-stu-id="54d16-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="54d16-326">手順については [、「Use PowerShell を使用してスパム対策ポリシーを作成する」を参照してください](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="54d16-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="54d16-327">この例では、次の設定を使用して、Research Department という名前の新しいスパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54d16-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="54d16-328">すべてのスパム フィルターの評決に対するアクションが [検疫] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="54d16-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="54d16-329">アクセス許可なしを割り当てる NoAccess という名前のカスタム検疫ポリシーは、既定でアクセス許可なしをまだ割り当てない既定の検疫ポリシーに置き換わります。 </span><span class="sxs-lookup"><span data-stu-id="54d16-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="54d16-330">構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="54d16-331">この例では、Human Resources という名前の既存のスパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="54d16-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="54d16-332">スパム検疫の評決のアクションは [検疫] に設定され、NoAccess という名前のカスタム検疫ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="54d16-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="54d16-333">構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="54d16-334">ポータルでグローバル検疫通知設定をMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="54d16-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="54d16-335">検疫ポリシーのグローバル設定を使用すると、検疫されたメッセージの受信者に送信されるエンドユーザーのスパム通知をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="54d16-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="54d16-336">これらの通知の詳細については、「エンドユーザーの [スパム通知」を参照してください](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="54d16-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="54d16-337">[セキュリティ ポータルMicrosoft 365 Defenderに移動し、[電子メール &**の** 脅威ポリシー] セクションの [検疫ポリシー] に移動し、[検疫ポリシー \>  \>  \>  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54d16-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="54d16-338">[検疫ポリシー **] ページで、[** グローバル設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54d16-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="54d16-339">開く **検疫通知設定の** フライアウトで、次の設定の一部またはすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="54d16-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="54d16-340">**表示名**: エンド ユーザーのスパム通知で使用される送信者の表示名をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="54d16-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="54d16-341">追加した言語ごとに、2 番目の言語ボックス ([X] をクリックしない) で言語を選択し、[表示名] ボックスに必要なテキスト値 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="54d16-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="54d16-342">次のスクリーンショットは、エンド ユーザーのスパム通知でカスタマイズされた表示名を示しています。</span><span class="sxs-lookup"><span data-stu-id="54d16-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![エンド ユーザースパム通知のカスタマイズされた送信者の表示名](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="54d16-344">**免責** 事項 : エンドユーザーのスパム通知の下部にカスタム免責事項を追加します。</span><span class="sxs-lookup"><span data-stu-id="54d16-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="54d16-345">ローカライズされたテキスト、 **組織からの免責事項:** は常に最初に含まれていて、その後に指定したテキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="54d16-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="54d16-346">追加した言語ごとに、2 番目の言語ボックス ([X] をクリックしない) で言語を選択し、[免責事項] ボックスに必要なテキスト値 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="54d16-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="54d16-347">次のスクリーンショットは、エンド ユーザーのスパム通知でカスタマイズされた免責事項を示しています。</span><span class="sxs-lookup"><span data-stu-id="54d16-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![エンドユーザーのスパム通知の下部にあるカスタム免責事項](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="54d16-349">**[言語の選択**]: エンド ユーザーのスパム通知は、受信者の言語設定に基づいて既にローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="54d16-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="54d16-350">表示名と免責事項の値には、異なる **言語でカスタマイズ** されたテキスト **を指定** できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="54d16-351">[最初の言語] ボックスから少なくとも 1 つの言語を選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="54d16-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="54d16-352">複数の言語を選択するには、[追加] をクリック **します** 。</span><span class="sxs-lookup"><span data-stu-id="54d16-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="54d16-353">セクションの言語ボックスには、選択した言語すべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54d16-353">A section language box shows all of the languages that you've selected:</span></span>

     ![検疫ポリシーのグローバル検疫通知設定の [2 番目の言語] ボックスで選択した言語](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="54d16-355">**[会社のロゴを使用** する]: エンド ユーザーのスパム通知の上部で使用される既定の Microsoft ロゴを置き換える場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="54d16-356">これを行う前に、「カスタム ロゴをアップロードするには、組織Microsoft 365テーマをカスタマイズする」の[指示](../../admin/setup/customize-your-organization-theme.md)に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="54d16-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="54d16-357">次のスクリーンショットは、エンドユーザーのスパム通知のカスタム ロゴを示しています。</span><span class="sxs-lookup"><span data-stu-id="54d16-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![エンドユーザースパム通知のカスタム ロゴ](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="54d16-359">Microsoft 365 Defender ポータルで検疫ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="54d16-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="54d16-360">[セキュリティ ポータルMicrosoft 365 Defenderに移動し、[電子メール &**の** 脅威ポリシー] セクションの [検疫ポリシー] に移動し、[検疫ポリシー \>  \>  \>  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54d16-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="54d16-361">[**検疫ポリシー] ページ** には、[名前]と [最終更新日] のポリシー **の一覧が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="54d16-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="54d16-362">組み込みまたはカスタム検疫ポリシーの設定を表示するには、名前をクリックして、一覧から検疫ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="54d16-363">グローバル設定を表示するには、[グローバル設定] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="54d16-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="54d16-364">PowerShell で検疫ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="54d16-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="54d16-365">PowerShell を使用して検疫ポリシーを表示する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="54d16-366">すべての組み込みポリシーまたはカスタム ポリシーの概要リストを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="54d16-367">組み込みまたはカスタム検疫ポリシーの設定を表示するには、検疫ポリシーの名前に置き換え、 \<QuarantinePolicyName\> 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="54d16-368">グローバル設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="54d16-369">構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="54d16-370">ポータルで検疫ポリシーをMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="54d16-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="54d16-371">[セキュリティ ポータルMicrosoft 365 Defenderに移動し、[電子メール &**の** 脅威ポリシー] セクションの [検疫ポリシー] に移動し、[検疫ポリシー \>  \>  \>  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54d16-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="54d16-372">[検疫 **ポリシー] ページで** 、名前をクリックしてポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="54d16-373">ポリシーを選択した後、[ポリシーの編集] アイコン ![ ](../../media/m365-cc-sc-edit-icon.png) **が表示される [ポリシーの編集** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d16-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="54d16-374">開 **くポリシーの** 編集ウィザードは、この記事の前の「Microsoft 365 Defender ポータルの検疫ポリシーの作成」で説明したように、新しいポリシー [ウィザードと](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)事実上同じです。</span><span class="sxs-lookup"><span data-stu-id="54d16-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="54d16-375">主な違いは、既存のポリシーの名前を変更できない点です。</span><span class="sxs-lookup"><span data-stu-id="54d16-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="54d16-376">ポリシーの変更が完了したら、[概要] ページに移動し、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="54d16-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="54d16-377">PowerShell で検疫ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="54d16-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="54d16-378">PowerShell を使用してカスタム検疫ポリシーを変更する場合は、検疫ポリシーの名前に置き換え、次の \<QuarantinePolicyName\> 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d16-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="54d16-379">使用可能な設定は、この記事で前述した検疫ポリシーの作成に関する説明と同じです。</span><span class="sxs-lookup"><span data-stu-id="54d16-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="54d16-380">構文とパラメーターの詳細については [、「Set-QuarantineTag」を参照してください](/powershell/module/exchange/set-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="54d16-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="54d16-381">セキュリティ ポータルで検疫ポリシーをMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="54d16-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="54d16-382">**注**:</span><span class="sxs-lookup"><span data-stu-id="54d16-382">**Notes**:</span></span>

- <span data-ttu-id="54d16-383">組み込みの検疫ポリシーを削除できない。</span><span class="sxs-lookup"><span data-stu-id="54d16-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="54d16-384">カスタム検疫ポリシーを削除する前に、そのポリシーが使用されていないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="54d16-385">たとえば、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="54d16-386">検疫ポリシーが使用されている場合は、割 [り当てられた検疫ポリシー](#step-2-assign-a-quarantine-policy-to-supported-features) を削除する前に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="54d16-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="54d16-387">[セキュリティ ポータルMicrosoft 365 Defenderに移動し、[電子メール &**の** 脅威ポリシー] セクションの [検疫ポリシー] に移動し、[検疫ポリシー \>  \>  \>  ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54d16-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="54d16-388">[検疫 **ポリシー] ページ** で、名前をクリックして削除するカスタム検疫ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54d16-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="54d16-389">ポリシーを選択した後、[ポリシーの削除] ![ アイコン ](../../media/m365-cc-sc-delete-icon.png) が表示される [ **ポリシーの** 削除] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d16-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="54d16-390">表示 **される確認ダイアログで** [ポリシーの削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d16-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="54d16-391">PowerShell で検疫ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="54d16-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="54d16-392">PowerShell を使用してカスタム検疫ポリシーを削除する場合は、検疫ポリシーの名前に置き換え、 \<QuarantinePolicyName\> 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d16-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="54d16-393">構文とパラメーターの詳細については [、「Remove-QuarantineTag」を参照してください](/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="54d16-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="54d16-394">検疫ポリシーのアクセス許可の詳細</span><span class="sxs-lookup"><span data-stu-id="54d16-394">Quarantine policy permission details</span></span>

<span data-ttu-id="54d16-395">次のセクションでは、検疫済みメッセージの詳細およびエンドユーザーのスパム通知における事前設定されたアクセス許可グループと個々のアクセス許可の影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="54d16-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="54d16-396">事前設定されたアクセス許可グループ</span><span class="sxs-lookup"><span data-stu-id="54d16-396">Preset permissions groups</span></span>

<span data-ttu-id="54d16-397">事前設定されたアクセス許可グループに含まれる個々のアクセス許可は、この記事の冒頭の表に示されています。</span><span class="sxs-lookup"><span data-stu-id="54d16-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="54d16-398">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="54d16-398">No access</span></span>

<span data-ttu-id="54d16-399">検疫ポリシーでアクセス許可なし(アクセス許可なし) が割り当て済みである場合、ユーザーは引き続きいくつかの基準機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="54d16-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="54d16-400">**検疫済みメッセージの詳細**: [ **メッセージ ヘッダーの表示] ボタン** は常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![検疫ポリシーでユーザーにアクセス許可がない場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="54d16-402">**エンドユーザーのスパム通知**: **検疫内** のメッセージにユーザーを移動する [確認] ボタンは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![検疫ポリシーでユーザーにアクセス許可がない場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="54d16-404">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-404">Limited access</span></span>

<span data-ttu-id="54d16-405">検疫ポリシーで制限付きアクセス許可 **が割り** 当てられている場合、ユーザーは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="54d16-406">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="54d16-407">**リリースの要求**</span><span class="sxs-lookup"><span data-stu-id="54d16-407">**Request release**</span></span>
  - <span data-ttu-id="54d16-408">**メッセージ ヘッダーの表示**</span><span class="sxs-lookup"><span data-stu-id="54d16-408">**View message header**</span></span>
  - <span data-ttu-id="54d16-409">**プレビュー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="54d16-409">**Preview message**</span></span>
  - <span data-ttu-id="54d16-410">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="54d16-410">**Block sender**</span></span>
  - <span data-ttu-id="54d16-411">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="54d16-411">**Remove from quarantine**</span></span>

  ![検疫ポリシーがユーザーに制限付きアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="54d16-413">**エンド ユーザーのスパム通知**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="54d16-414">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="54d16-414">**Block sender**</span></span>
  - <span data-ttu-id="54d16-415">**確認**</span><span class="sxs-lookup"><span data-stu-id="54d16-415">**Review**</span></span>

  ![検疫ポリシーがユーザーに制限付きアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="54d16-417">フル アクセス</span><span class="sxs-lookup"><span data-stu-id="54d16-417">Full access</span></span>

<span data-ttu-id="54d16-418">検疫ポリシーで [フル アクセス] **アクセス許可** (すべての使用可能なアクセス許可) が割り当て済みである場合、ユーザーは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="54d16-419">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="54d16-420">**リリース メッセージ**</span><span class="sxs-lookup"><span data-stu-id="54d16-420">**Release message**</span></span>
  - <span data-ttu-id="54d16-421">**メッセージ ヘッダーの表示**</span><span class="sxs-lookup"><span data-stu-id="54d16-421">**View message header**</span></span>
  - <span data-ttu-id="54d16-422">**プレビュー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="54d16-422">**Preview message**</span></span>
  - <span data-ttu-id="54d16-423">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="54d16-423">**Block sender**</span></span>
  - <span data-ttu-id="54d16-424">**送信者を許可する**</span><span class="sxs-lookup"><span data-stu-id="54d16-424">**Allow sender**</span></span>
  - <span data-ttu-id="54d16-425">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="54d16-425">**Remove from quarantine**</span></span>

  ![検疫ポリシーがユーザーにフル アクセスのアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="54d16-427">**エンド ユーザーのスパム通知**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="54d16-428">**送信者をブロックする**</span><span class="sxs-lookup"><span data-stu-id="54d16-428">**Block sender**</span></span>
  - <span data-ttu-id="54d16-429">**リリース**</span><span class="sxs-lookup"><span data-stu-id="54d16-429">**Release**</span></span>
  - <span data-ttu-id="54d16-430">**確認**</span><span class="sxs-lookup"><span data-stu-id="54d16-430">**Review**</span></span>

  ![検疫ポリシーがユーザーにフル アクセスのアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="54d16-432">個々のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="54d16-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="54d16-433">ユーザーは、[アクセスなし] セクションで説明されているボタンを常 [に取得](#no-access) します。</span><span class="sxs-lookup"><span data-stu-id="54d16-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="54d16-434">これらのボタンは、個々のアクセス許可の説明には含まれません。</span><span class="sxs-lookup"><span data-stu-id="54d16-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="54d16-435">送信者のアクセス許可を許可する</span><span class="sxs-lookup"><span data-stu-id="54d16-435">Allow sender permission</span></span>

<span data-ttu-id="54d16-436">[**送信者の許可**]_(PermissionToAllowSender)_ はボタンへのアクセスを制御し、検疫済みメッセージ送信者を [送信者] リストに簡単に追加セーフします。</span><span class="sxs-lookup"><span data-stu-id="54d16-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="54d16-437">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="54d16-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="54d16-438">**[送信者のアクセス許可** を有効にする]: [送信者 **を許可する** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="54d16-439">**[送信者のアクセス許可** を無効にする]: [送信者 **を許可する** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="54d16-440">**エンド ユーザーのスパム通知**: 無効です。</span><span class="sxs-lookup"><span data-stu-id="54d16-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="54d16-441">セーフ 送信者の一覧の詳細については、「信頼できる送信者が[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)ブロックされるのを防ぐ」および[「use Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスのセーフリスト コレクションを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="54d16-442">送信者のアクセス許可をブロックする</span><span class="sxs-lookup"><span data-stu-id="54d16-442">Block sender permission</span></span>

<span data-ttu-id="54d16-443">[ **送信者のブロック]** アクセス許可 _(PermissionToBlockSender)_ はボタンへのアクセスを制御し、検疫済みメッセージ送信者をブロックされた送信者リストに簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="54d16-444">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="54d16-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="54d16-445">**[送信者のアクセス許可** をブロックする] を有効にする: **[送信者のブロック** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="54d16-446">**[送信者のアクセス許可** を無効にする]: [ **送信者のブロック** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="54d16-447">**エンド ユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="54d16-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="54d16-448">**[送信者のアクセス許可** を無効にする]: [ **送信者のブロック** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="54d16-449">**[送信者のアクセス許可** をブロックする] を有効にする: **[送信者のブロック** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="54d16-450">[送信者のブロック] リストの詳細については、「他[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)のユーザーからのメッセージをブロックする」および[「Use Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスのセーフリスト コレクションを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d16-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="54d16-451">削除のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="54d16-451">Delete permission</span></span>

<span data-ttu-id="54d16-452">[ **削除]** アクセス許可 _(PermissionToDelete)_ は、ユーザーが検疫からメッセージ (ユーザーが受信者であるメッセージ) を削除する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="54d16-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="54d16-453">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="54d16-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="54d16-454">**アクセス許可** の削除が有効: [ **検疫から削除] ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="54d16-455">**削除** のアクセス許可が無効: [ **検疫から削除] ボタン** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="54d16-456">**エンド ユーザーのスパム通知**: 無効です。</span><span class="sxs-lookup"><span data-stu-id="54d16-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="54d16-457">プレビューのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="54d16-457">Preview permission</span></span>

<span data-ttu-id="54d16-458">[ **プレビュー]** アクセス許可 _(PermissionToPreview)_ は、ユーザーが検疫でメッセージをプレビューする機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="54d16-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="54d16-459">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="54d16-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="54d16-460">**プレビュー** のアクセス許可が有効: **[メッセージのプレビュー] ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="54d16-461">**プレビュー** のアクセス許可が無効: **[メッセージのプレビュー]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="54d16-462">**エンド ユーザーのスパム通知**: 無効です。</span><span class="sxs-lookup"><span data-stu-id="54d16-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="54d16-463">受信者が検疫のアクセス許可からメッセージを解放するを許可する</span><span class="sxs-lookup"><span data-stu-id="54d16-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="54d16-464">[ **受信者に検疫** からのメッセージの解放を許可する] アクセス許可 _(PermissionToRelease)_ は、ユーザーが管理者の承認なしに検疫済みメッセージを直接解放する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="54d16-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="54d16-465">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="54d16-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="54d16-466">アクセス許可が有効: **[メッセージの解放] ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="54d16-467">アクセス許可が無効: **[メッセージの解放]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="54d16-468">**エンド ユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="54d16-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="54d16-469">アクセス許可が有効: **[リリース]** ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="54d16-470">アクセス許可が無効: **[リリース]** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="54d16-471">受信者が検疫アクセス許可からメッセージを解放する要求を許可する</span><span class="sxs-lookup"><span data-stu-id="54d16-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="54d16-472">[**受信者に検疫** からのメッセージの解放を要求する] アクセス許可 _(PermissionToRequestRelease)_ は、ユーザーが検疫済みメッセージのリリースを要求する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="54d16-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="54d16-473">メッセージは、管理者が要求を承認した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="54d16-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="54d16-474">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="54d16-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="54d16-475">アクセス許可が有効: **[要求] リリース ボタン** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d16-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="54d16-476">アクセス許可が無効: **[要求] リリース** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="54d16-477">**エンドユーザーのスパム通知**: [ **リリース] ボタン** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="54d16-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
