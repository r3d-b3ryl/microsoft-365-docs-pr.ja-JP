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
description: 管理者は、Exchange Online Protection ハイブリッド環境でスパムをユーザーの迷惑メール フォルダーにルーティングする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167121"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="ada6a-103">ハイブリッド環境で迷惑メール フォルダーにスパムを配信するスタンドアロン EOP を構成する</span><span class="sxs-lookup"><span data-stu-id="ada6a-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ada6a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ada6a-104">**Applies to**</span></span>
-  [<span data-ttu-id="ada6a-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="ada6a-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> <span data-ttu-id="ada6a-106">このトピックは、ハイブリッド環境のスタンドアロン EOP のお客様向けです。</span><span class="sxs-lookup"><span data-stu-id="ada6a-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="ada6a-107">このトピックは、Exchange Online メールボックスを使用している Microsoft 365 のお客様には適用されません。</span><span class="sxs-lookup"><span data-stu-id="ada6a-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="ada6a-108">ハイブリッド環境でスタンドアロンの Exchange Online Protection (EOP) を使用している場合は、EOP のスパム フィルターの判断を認識して翻訳するようにオンプレミスの Exchange 組織を構成する必要があります。そのため、オンプレミスのメールボックスの迷惑メール ルールがメッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="ada6a-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="ada6a-109">具体的には、次の EOP スパム対策ヘッダーと値を持つメッセージを検索する条件、およびそれらのメッセージの Spam Confidence Level (SCL) を 6 に設定するアクションを使用して、オンプレミスの Exchange 組織にメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada6a-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="ada6a-110">`X-Forefront-Antispam-Report: SFV:SPM` (スパム フィルタリングによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="ada6a-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="ada6a-111">`X-Forefront-Antispam-Report: SFV:SKS` (スパム フィルタリングの前に EOP のメール フロー ルールによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="ada6a-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="ada6a-112">`X-Forefront-Antispam-Report: SFV:SKB` (送信者の電子メール アドレスまたは電子メール ドメインが受信拒否リストまたは EOP のブロックされたドメインの一覧にある場合に、スパム フィルターによってスパムとしてマークされたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="ada6a-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="ada6a-113">これらのヘッダー値の詳細については、「スパム対策メッセージ ヘッダー [」を参照してください](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="ada6a-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="ada6a-114">このトピックでは、Exchange 管理センター (EAC) およびオンプレミスの Exchange 組織の Exchange 管理シェル (Exchange PowerShell) でこれらのメール フロー ルールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="ada6a-115">オンプレミス ユーザーの迷惑メール フォルダーにメッセージを配信する代わりに、EOP でスパム対策ポリシーを構成して、EOP でスパム メッセージを検疫できます。</span><span class="sxs-lookup"><span data-stu-id="ada6a-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="ada6a-116">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada6a-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ada6a-117">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ada6a-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ada6a-118">これらの手順を実行する前に、オンプレミスの Exchange 環境でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada6a-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="ada6a-119">具体的には、既定で組織の管理、コンプライアンス管理、およびレコード管理の役割に割り当てられるトランスポート ルールの役割を割り当てる必要があります。 </span><span class="sxs-lookup"><span data-stu-id="ada6a-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="ada6a-120">詳細については、「役割グループに [メンバーを追加する」を参照してください](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)。</span><span class="sxs-lookup"><span data-stu-id="ada6a-120">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="ada6a-121">メッセージがオンプレミスの Exchange 組織の迷惑メール フォルダーに配信される場合と配信される場合は、次の設定の組み合わせによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="ada6a-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="ada6a-122">Exchange 管理シェル の [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)コマンドレットの _SCLJunkThreshold_ パラメーター値。</span><span class="sxs-lookup"><span data-stu-id="ada6a-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="ada6a-123">既定値は 4 で、SCL が 5 以上の場合はユーザーの迷惑メール フォルダーにメッセージを配信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada6a-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="ada6a-124">Exchange 管理シェル の [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)コマンドレットの _SCLJunkThreshold_ パラメーター値。</span><span class="sxs-lookup"><span data-stu-id="ada6a-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="ada6a-125">既定値は空白 ($null) で、組織の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ada6a-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="ada6a-126">詳細については [、「Exchange Spam Confidence Level (SCL) のしきい値」を参照してください](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)。</span><span class="sxs-lookup"><span data-stu-id="ada6a-126">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="ada6a-127">メールボックスで迷惑メール ルールを有効にするかどうかを指定します _(Enabled_ パラメーターの値は、Exchange 管理シェル の [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) コマンドレットで $true です)。</span><span class="sxs-lookup"><span data-stu-id="ada6a-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="ada6a-128">配信後に実際にメッセージを迷惑メール フォルダーに移動する迷惑メール ルールです。</span><span class="sxs-lookup"><span data-stu-id="ada6a-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="ada6a-129">既定では、迷惑メール ルールはメールボックスで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ada6a-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="ada6a-130">詳細については、「[Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada6a-130">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="ada6a-131">Exchange 管理センターで EAC を開[Exchange Server、Exchange 管理センターを参照Exchange Server。](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="ada6a-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="ada6a-132">Exchange 管理シェル を開くには、「[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada6a-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="ada6a-133">オンプレミスの Exchange のメール フロー ルールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada6a-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="ada6a-134">Exchange Server のメール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="ada6a-134">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="ada6a-135">メール フロー ルールの条件と例外 (述語) Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ada6a-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="ada6a-136">メール フロー ルールのアクション (Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ada6a-136">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="ada6a-137">EAC を使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="ada6a-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="ada6a-138">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ada6a-139">[**追加]** アイコンをクリックし、表示されるドロップダウンで [新しいルール ![ ](../../media/ITPro-EAC-AddIcon.png) の作成] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="ada6a-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="ada6a-140">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="ada6a-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ada6a-141">**[名前**]: ルールのわかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="ada6a-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-142">For example:</span></span>

     - <span data-ttu-id="ada6a-143">EOP SFV:SPM から SCL 6</span><span class="sxs-lookup"><span data-stu-id="ada6a-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="ada6a-144">EOP SFV:SKS から SCL 6</span><span class="sxs-lookup"><span data-stu-id="ada6a-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="ada6a-145">EOP SFV:SKB から SCL 6</span><span class="sxs-lookup"><span data-stu-id="ada6a-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="ada6a-146">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ada6a-146">Click **More Options**.</span></span>

   - <span data-ttu-id="ada6a-147">**メッセージ ヘッダーに次の** 単語が **含まれる** 場合 \> **に、このルールを適用します**。</span><span class="sxs-lookup"><span data-stu-id="ada6a-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="ada6a-148">Enter テキスト **ヘッダーに表示される Enter words** 文が含まれる場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="ada6a-149">[テキスト **の入力] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ada6a-149">Click **Enter text**.</span></span> <span data-ttu-id="ada6a-150">表示される [ **ヘッダー名の** 指定] ダイアログで **、「X-Forefront-Antispam-Report」** と入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ada6a-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="ada6a-151">[単語  **の入力] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ada6a-151">Click  **Enter words**.</span></span> <span data-ttu-id="ada6a-152">表示される[単語または語句の指定] ダイアログで、EOP スパム ヘッダー値 (**SFV:SPM、SFV:SKS、** または **SFV:SKB)** の 1 つを入力し、[追加] アイコンをクリックし ![ ](../../media/ITPro-EAC-AddIcon.png) **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ada6a-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="ada6a-153">**Do the following**: Select **Modify the message properties** Set the spam confidence level \> **(SCL)**.</span><span class="sxs-lookup"><span data-stu-id="ada6a-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="ada6a-154">表示される **[SCL の** 指定] ダイアログで **、6** (既定値は **5) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada6a-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="ada6a-155">完了したら、[保存] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="ada6a-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="ada6a-156">残りの EOP スパム判断値 **(SFV:SPM、SFV:SKS、\*\*\*\*または SFV:SKB)** に対して、これらの手順を繰り返します。 </span><span class="sxs-lookup"><span data-stu-id="ada6a-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="ada6a-157">Exchange 管理シェル を使用して、EOP スパム メッセージの SCL を設定するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="ada6a-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="ada6a-158">次の構文を使用して、3 つのメール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="ada6a-159">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="ada6a-160">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada6a-160">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ada6a-161">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="ada6a-161">How do you know this worked?</span></span>

<span data-ttu-id="ada6a-162">ハイブリッド環境の迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP が正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="ada6a-163">EAC で、[メールフロー ルール] に移動し、ルールを選択して、[編集] アイコンをクリックして設定 \>  ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="ada6a-164">Exchange 管理シェル で、メール フロー ルールの名前に置き換え、次のコマンドを使用して設定 \<RuleName\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="ada6a-165">スパムの送信メッセージをスキャンしない外部の電子メール システムで、影響を受ける受信者に迷惑メール (GTUBE) メッセージの汎用テストを送信し、迷惑メール フォルダーに配信されるか確認します。</span><span class="sxs-lookup"><span data-stu-id="ada6a-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="ada6a-166">GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="ada6a-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="ada6a-167">GTUBE メッセージを送信するには、スペースや改行を使用せずに、電子メール メッセージの本文に次のテキストを 1 行に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada6a-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
