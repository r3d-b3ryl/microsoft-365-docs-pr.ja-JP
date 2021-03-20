---
title: ハイブリッド環境で迷惑メールに EOP を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection ハイブリッド環境のユーザー迷惑メール フォルダーにスパムをルーティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910860"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="3003a-103">ハイブリッド環境の迷惑メール フォルダーにスパムを配信するスタンドアロン EOP を構成する</span><span class="sxs-lookup"><span data-stu-id="3003a-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3003a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3003a-104">**Applies to**</span></span>
-  [<span data-ttu-id="3003a-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="3003a-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="3003a-106">このトピックは、ハイブリッド環境のスタンドアロン EOP のお客様専用です。</span><span class="sxs-lookup"><span data-stu-id="3003a-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="3003a-107">このトピックは、Exchange Online メールボックスを使用している Microsoft 365 のお客様には適用されません。</span><span class="sxs-lookup"><span data-stu-id="3003a-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="3003a-108">ハイブリッド環境でスタンドアロンの Exchange Online Protection (EOP) のお客様である場合は、EOP のスパム フィルターの評決を認識して翻訳するようにオンプレミスの Exchange 組織を構成する必要があります。そのため、オンプレミスメールボックスの迷惑メール ルールはメッセージを迷惑メール フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="3003a-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="3003a-109">具体的には、次の EOP スパム対策ヘッダーと値を含むメッセージを検索する条件、およびこれらのメッセージのスパム信頼レベル (SCL) を 6 に設定するアクションを使用して、オンプレミスの Exchange 組織にメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3003a-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="3003a-110">`X-Forefront-Antispam-Report: SFV:SPM` (スパム フィルターによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="3003a-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="3003a-111">`X-Forefront-Antispam-Report: SFV:SKS` (スパム フィルター処理の前に EOP でメール フロー ルールによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="3003a-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="3003a-112">`X-Forefront-Antispam-Report: SFV:SKB` (送信者の電子メール アドレスまたは電子メール ドメインがブロックされた送信者リストまたは EOP のブロックされたドメイン リストに含め、スパム フィルターによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="3003a-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="3003a-113">これらのヘッダー値の詳細については、「スパム対策メッセージ [ヘッダー」を参照してください](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="3003a-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="3003a-114">このトピックでは、Exchange 管理センター (EAC) およびオンプレミス Exchange 組織の Exchange 管理シェル (Exchange PowerShell) で、これらのメール フロー ルールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3003a-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="3003a-115">メッセージをオンプレミスユーザーの迷惑メール フォルダーに配信する代わりに、EOP でスパムメッセージを検疫するスパム対策ポリシーを EOP で構成できます。</span><span class="sxs-lookup"><span data-stu-id="3003a-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="3003a-116">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3003a-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3003a-117">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="3003a-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3003a-118">これらの手順を実行するには、オンプレミスの Exchange 環境でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3003a-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="3003a-119">具体的には、既定で組織の管理、コンプライアンス管理、およびレコード管理の役割に割り当てられているトランスポート ルールの役割を割り当てる必要があります。 </span><span class="sxs-lookup"><span data-stu-id="3003a-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="3003a-120">詳細については、「役割グループに [メンバーを追加する」を参照してください](/Exchange/permissions/role-group-members#add-members-to-a-role-group)。</span><span class="sxs-lookup"><span data-stu-id="3003a-120">For more information, see [Add members to a role group](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="3003a-121">オンプレミスの Exchange 組織の迷惑メール フォルダーにメッセージが配信される場合と配信される場合は、次の設定の組み合わせによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="3003a-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="3003a-122">Exchange 管理シェルの [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)コマンドレットの _SCLJunkThreshold_ パラメーター値。</span><span class="sxs-lookup"><span data-stu-id="3003a-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="3003a-123">既定値は 4 です。つまり、SCL が 5 以上の場合は、ユーザーの迷惑メール フォルダーにメッセージを配信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3003a-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="3003a-124">Exchange 管理シェルの [Set-Mailbox](/powershell/module/exchange/set-mailbox)コマンドレットの _SCLJunkThreshold_ パラメーター値。</span><span class="sxs-lookup"><span data-stu-id="3003a-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="3003a-125">既定値は空白 ($null) で、組織の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3003a-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="3003a-126">詳細については [、「Exchange スパム信頼レベル (SCL) のしきい値」を参照してください](/Exchange/antispam-and-antimalware/antispam-protection/scl)。</span><span class="sxs-lookup"><span data-stu-id="3003a-126">For details, see [Exchange spam confidence level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="3003a-127">メールボックスで迷惑メール ルールが有効になっているかどうか (Exchange管理シェルの[Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration)コマンドレットの Enabled パラメーター値は $true です)。</span><span class="sxs-lookup"><span data-stu-id="3003a-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="3003a-128">配信後にメッセージを迷惑メール フォルダーに実際に移動する迷惑メール ルールです。</span><span class="sxs-lookup"><span data-stu-id="3003a-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="3003a-129">既定では、迷惑メール ルールはメールボックスで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3003a-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="3003a-130">詳細については、「[Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3003a-130">For more information, see [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="3003a-131">EAC を開く方法については、「Exchange Server Exchange[管理センター」を参照Exchange Server。](/Exchange/architecture/client-access/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="3003a-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="3003a-132">Exchange 管理シェル を開くには、「[Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3003a-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="3003a-133">オンプレミス Exchange のメール フロー ルールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3003a-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="3003a-134">メール フロー ルール (Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3003a-134">Mail flow rules in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="3003a-135">メール フロー ルールの条件と例外 (述語) Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3003a-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="3003a-136">メール フロー ルールのアクション (Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3003a-136">Mail flow rule actions in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="3003a-137">EAC を使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="3003a-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="3003a-138">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3003a-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="3003a-139">[**追加]** ![ アイコンをクリックし、表示されるドロップダウンで [新しいルールを作成 ](../../media/ITPro-EAC-AddIcon.png) する] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="3003a-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="3003a-140">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="3003a-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3003a-141">**名前**: ルールの一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3003a-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="3003a-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3003a-142">For example:</span></span>

     - <span data-ttu-id="3003a-143">EOP SFV:SPM to SCL 6</span><span class="sxs-lookup"><span data-stu-id="3003a-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="3003a-144">EOP SFV:SKS to SCL 6</span><span class="sxs-lookup"><span data-stu-id="3003a-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="3003a-145">EOP SFV:SKB to SCL 6</span><span class="sxs-lookup"><span data-stu-id="3003a-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="3003a-146">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3003a-146">Click **More Options**.</span></span>

   - <span data-ttu-id="3003a-147">**[メッセージ ヘッダーに次** の単語が **含** まれる] の \> **場合は、このルールを適用します**。</span><span class="sxs-lookup"><span data-stu-id="3003a-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="3003a-148">[Enter **text] ヘッダーに表示される Enter words 文** が含まれています。次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3003a-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="3003a-149">[テキスト **の入力] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3003a-149">Click **Enter text**.</span></span> <span data-ttu-id="3003a-150">表示される **[ヘッダー名の指定]** ダイアログで **、「X-Forefront-Antispam-Report」** と入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3003a-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="3003a-151">[単語  **の入力] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3003a-151">Click  **Enter words**.</span></span> <span data-ttu-id="3003a-152">表示される [単語または語句の指定] ダイアログで、EOP スパム ヘッダー値 **(SFV:SPM、SFV:SKS、** または **SFV:SKB)** のいずれかを入力し、[追加] アイコンをクリックし ![ ](../../media/ITPro-EAC-AddIcon.png) **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3003a-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="3003a-153">**[メッセージのプロパティを** 変更 **する]** [ \> **スパム信頼レベル (SCL) の設定] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3003a-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="3003a-154">表示される **[SCL の指定** ] ダイアログで **、[6]** (既定値は **5) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3003a-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="3003a-155">完了したら、[保存] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="3003a-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="3003a-156">残りの EOP スパムの評決値 **(SFV:SPM、SFV:SKS、\*\*\*\*または SFV:SKB)** に対して、次の手順を繰り返します。 </span><span class="sxs-lookup"><span data-stu-id="3003a-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="3003a-157">Exchange 管理シェルを使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="3003a-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="3003a-158">次の構文を使用して、3 つのメール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="3003a-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="3003a-159">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3003a-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="3003a-160">詳細な構文とパラメーターについては、「[New-TransportRule](/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3003a-160">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3003a-161">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="3003a-161">How do you know this worked?</span></span>

<span data-ttu-id="3003a-162">ハイブリッド環境の迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP が正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3003a-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="3003a-163">EAC で、[メールフロールール] に移動し、ルールを選択し、[編集] アイコンをクリックして設定 \>  ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。</span><span class="sxs-lookup"><span data-stu-id="3003a-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="3003a-164">Exchange 管理シェルで、メール フロー ルールの名前に置き換え、次のコマンドを実行して設定 \<RuleName\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="3003a-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="3003a-165">スパムの送信メッセージをスキャンしない外部電子メール システムで、影響を受ける受信者に一般一括メール (GTUBE) メッセージを送信し、そのメッセージが迷惑メール フォルダーに配信されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="3003a-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="3003a-166">GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="3003a-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="3003a-167">GTUBE メッセージを送信するには、1 行の電子メール メッセージの本文に、スペースや改行を含めずに、次のテキストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3003a-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```