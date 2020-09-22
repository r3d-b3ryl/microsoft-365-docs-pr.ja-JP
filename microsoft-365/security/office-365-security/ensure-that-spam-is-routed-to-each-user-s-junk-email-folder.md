---
title: ハイブリッド環境で EOP を迷惑メールに構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection ハイブリッド環境でスパムをユーザーの迷惑メールフォルダーにルーティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4c01ad0e8efa4d28e1b5d1e72b3daa87bb01b619
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196595"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="6690d-103">ハイブリッド環境で迷惑メールフォルダーにスパムを配信するようにスタンドアロン EOP を構成する</span><span class="sxs-lookup"><span data-stu-id="6690d-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="6690d-104">このトピックは、ハイブリッド環境のスタンドアロン EOP のお客様のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="6690d-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="6690d-105">このトピックは、Exchange Online メールボックスを使用している Microsoft 365 のお客様には適用されません。</span><span class="sxs-lookup"><span data-stu-id="6690d-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="6690d-106">ハイブリッド環境でのスタンドアロンの Exchange Online Protection (EOP) のお客様の場合は、オンプレミスの Exchange 組織を構成して、EOP のスパムフィルタリング verdicts を認識して変換する必要があります。このため、社内メールボックスの迷惑メールルールは、メッセージを [迷惑メール] フォルダーに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="6690d-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="6690d-107">具体的には、オンプレミスの Exchange 組織内のメールフロールール (トランスポートルールとも呼ばれます) を、次の EOP スパム対策のヘッダーおよび値のいずれかで検索する条件と、それらのメッセージのスパム信頼レベル (SCL) を6に設定するアクションを使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6690d-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="6690d-108">`X-Forefront-Antispam-Report: SFV:SPM` (スパムフィルターでスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="6690d-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="6690d-109">`X-Forefront-Antispam-Report: SFV:SKS` (スパムフィルター処理の前に EOP のメールフロールールによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="6690d-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="6690d-110">`X-Forefront-Antispam-Report: SFV:SKB` (送信者の電子メールアドレスまたは電子メールドメインが EOP のブロックされた送信者の一覧または禁止ドメインの一覧に含まれているため、スパムフィルターによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="6690d-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="6690d-111">これらのヘッダー値の詳細については、「 [スパム対策メッセージヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="6690d-112">このトピックでは、Exchange 管理センター (EAC) および社内 Exchange 組織の Exchange 管理シェル (Exchange PowerShell) で、これらのメールフロールールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6690d-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="6690d-113">オンプレミスのユーザーの迷惑メールフォルダーにメッセージを配信する代わりに、EOP でスパム対策ポリシーを構成して、EOP でスパムメッセージを検疫することができます。</span><span class="sxs-lookup"><span data-stu-id="6690d-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="6690d-114">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6690d-115">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="6690d-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6690d-116">これらの手順を実行する前に、オンプレミスの Exchange 環境でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6690d-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="6690d-117">具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6690d-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="6690d-118">詳細については、「 [役割グループにメンバーを追加する](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="6690d-119">オンプレミスの Exchange 組織の迷惑メールフォルダーにメッセージを配信する場合は、次の設定の組み合わせによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="6690d-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="6690d-120">Exchange 管理シェルの _SCLJunkThreshold_ コマンド [レットのパラメーター](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) の値。</span><span class="sxs-lookup"><span data-stu-id="6690d-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="6690d-121">既定値は4で、SCL が5以上の場合は、ユーザーの迷惑メールフォルダーにメッセージを配信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6690d-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="6690d-122">Exchange 管理シェルの[メールボックス](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)の_SCLJunkThreshold_コマンドレットのパラメーター値。</span><span class="sxs-lookup"><span data-stu-id="6690d-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="6690d-123">既定値は空白 ($null) で、組織の設定が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6690d-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="6690d-124">詳細については、「 [Exchange スパム信頼レベル (SCL) のしきい値](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="6690d-125">メールボックスで迷惑メールルールが有効になっているかどうか ( _enabled_ パラメーターの値は、Exchange 管理シェルの [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) コマンドレットでは $true。</span><span class="sxs-lookup"><span data-stu-id="6690d-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="6690d-126">これは、配信後にメッセージを [迷惑メール] フォルダーに実際に移動する迷惑メールルールです。</span><span class="sxs-lookup"><span data-stu-id="6690d-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="6690d-127">既定では、メールボックスで迷惑メールルールが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6690d-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="6690d-128">詳細については、「[Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="6690d-129">Exchange サーバー上の EAC を開くには、「exchange [server の exchange 管理センター](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="6690d-130">Exchange 管理シェルを開くには、「 [open The Exchange Management shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="6690d-131">オンプレミスの Exchange のメールフロールールの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="6690d-132">Exchange Server のメールフロールール</span><span class="sxs-lookup"><span data-stu-id="6690d-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="6690d-133">Exchange Server のメールフロールールの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="6690d-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="6690d-134">Exchange Server でのメールフロールールのアクション</span><span class="sxs-lookup"><span data-stu-id="6690d-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="6690d-135">EAC を使用して、EOP スパムメッセージの SCL を設定するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="6690d-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="6690d-136">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6690d-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="6690d-137">[追加] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) 、表示されるドロップダウンで [ **新しいルールの作成** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6690d-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="6690d-138">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="6690d-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="6690d-139">[**名前**]: わかりやすい一意のルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6690d-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="6690d-140">例:</span><span class="sxs-lookup"><span data-stu-id="6690d-140">For example:</span></span>

     - <span data-ttu-id="6690d-141">EOP SFV: SPM から SCL 6</span><span class="sxs-lookup"><span data-stu-id="6690d-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="6690d-142">EOP SFV: SFV から SCL 6</span><span class="sxs-lookup"><span data-stu-id="6690d-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="6690d-143">EOP SFV: SKB から SCL 6</span><span class="sxs-lookup"><span data-stu-id="6690d-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="6690d-144">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6690d-144">Click **More Options**.</span></span>

   - <span data-ttu-id="6690d-145">[次の**場合、このルールを適用**する]:**メッセージヘッダーを選択すると**、 \> **これらの単語のいずれかが含まれ**ます。</span><span class="sxs-lookup"><span data-stu-id="6690d-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="6690d-146">[ **テキストのヘッダーに語句を入力** してください] が表示されている場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6690d-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="6690d-147">[ **テキストの入力] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="6690d-147">Click **Enter text**.</span></span> <span data-ttu-id="6690d-148">表示される [ **ヘッダー名の指定** ] ダイアログで、「 **X-スパム対策-Report** 」と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6690d-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="6690d-149">[  **単語の入力] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="6690d-149">Click  **Enter words**.</span></span> <span data-ttu-id="6690d-150">表示された [ **単語または語句の指定** ] ダイアログボックスで、EOP スパムヘッダー値 (**SFV: SPM**、 **sfv: Sfv**、または **sfv: SKB**) のいずれかを入力し、 **[追加**] アイコンをクリックして、[ ![ ](../../media/ITPro-EAC-AddIcon.png) **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6690d-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="6690d-151">**次の操作を行い**ます。 [ **メッセージのプロパティを変更する**] [ \> **スパム信頼レベル (SCL) を設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6690d-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="6690d-152">表示される [ **SCL の指定** ] ダイアログで、[ **6** ] (既定値は **5**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6690d-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="6690d-153">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6690d-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="6690d-154">残りの EOP spam verdict 値 (**Sfv: SPM**、 **SFV: sfv**、または **sfv: SKB**) に対して、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6690d-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="6690d-155">Exchange 管理シェルを使用して、EOP スパムメッセージの SCL を設定するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="6690d-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="6690d-156">3つのメールフロールールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6690d-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="6690d-157">例:</span><span class="sxs-lookup"><span data-stu-id="6690d-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="6690d-158">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6690d-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6690d-159">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="6690d-159">How do you know this worked?</span></span>

<span data-ttu-id="6690d-160">ハイブリッド環境で迷惑メールフォルダーにスパムを配信するようにスタンドアロン EOP が正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6690d-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="6690d-161">EAC で、[**メールフロー**ルール] に移動し、 \> **Rules**ルールを選択して**Edit**から、[edit ![ edit] アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) て設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6690d-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="6690d-162">Exchange 管理シェルで、を \<RuleName\> メールフロールールの名前に置き換え、次のコマンドを使用して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6690d-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="6690d-163">**スパムの送信メッセージをスキャンしない**外部電子メールシステムでは、要求されていないバルクメール (gtube) メッセージの汎用テストを、影響を受ける受信者に送信し、迷惑メールフォルダーに配信されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6690d-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="6690d-164">GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="6690d-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="6690d-165">GTUBE メッセージを送信するには、電子メールメッセージの本文に、スペースや改行を含めずに、次のテキストを1行で入力します。</span><span class="sxs-lookup"><span data-stu-id="6690d-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
