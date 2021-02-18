---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理者は、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、ユーザーが Microsoft に報告するメッセージのコピーを受信する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287607"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="0101f-103">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="0101f-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0101f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0101f-104">**Applies to**</span></span>
- [<span data-ttu-id="0101f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0101f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0101f-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0101f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0101f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0101f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="0101f-108">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、「メッセージとファイルを [Microsoft](report-junk-email-messages-to-microsoft.md)に報告する」の説明に従って、ユーザーが分析のためにメッセージを Microsoft に報告する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="0101f-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="0101f-109">ユーザーが Microsoft に報告するメッセージを探すメール フロー ルール (トランスポート ルールとも呼ばれる) を作成し、報告されたメッセージのコピーを受信する BCC 受信者を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0101f-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="0101f-110">メール フロー ルールは、Exchange 管理センター (EAC) と PowerShell (Exchange Online のメールボックスを使用する Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で作成できます。</span><span class="sxs-lookup"><span data-stu-id="0101f-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0101f-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0101f-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0101f-112">この記事の手順を実行する前に、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0101f-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="0101f-113">具体的には、既定で組織の管理、コンプライアンス管理 **(グローバル** 管理者)、および **レコード** 管理の役割グループに割り当てられるトランスポート ルールの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="0101f-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="0101f-114">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0101f-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="0101f-115">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0101f-115">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="0101f-116">スタンドアロン EOP のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0101f-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="0101f-117">EAC を使用して役割グループのメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="0101f-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="0101f-118">Exchange Online で EAC を開く方法については [、Exchange Online の Exchange 管理センターを参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="0101f-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="0101f-119">スタンドアロン EOP で EAC を開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="0101f-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0101f-120">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0101f-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0101f-121">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0101f-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0101f-122">Exchange Online およびスタンドアロン EOP のメール フロー ルールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0101f-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="0101f-123">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="0101f-123">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="0101f-124">Exchange Online のメール フロー ルールでの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="0101f-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="0101f-125">Exchange Online でのメール フロー ルールの処理</span><span class="sxs-lookup"><span data-stu-id="0101f-125">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="0101f-126">EAC を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="0101f-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="0101f-127">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0101f-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="0101f-128">[追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルールの **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0101f-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="0101f-129">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="0101f-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="0101f-130">**[名前**]: ルールのわかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0101f-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="0101f-131">たとえば、BCC メッセージは Microsoft に報告されます。</span><span class="sxs-lookup"><span data-stu-id="0101f-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="0101f-132">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0101f-132">Click **More Options**.</span></span>

   - <span data-ttu-id="0101f-133">[受信者のアドレスに次のいずれかの単語が含まれる場合に適用する]: 表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[追加] アイコンをクリックして、すべての値を入力するまで繰り返します。 \>    ![ ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="0101f-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="0101f-134">エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="0101f-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="0101f-135">エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="0101f-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="0101f-136">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0101f-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="0101f-137">**[BCC ボックスに** 受信者 **を追加する**] を \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0101f-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="0101f-138">表示されるダイアログで、追加する受信者を見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="0101f-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="0101f-139">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0101f-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="0101f-140">追加の選択を行って、ルールの監査、ルールのテスト、特定の期間のルールのアクティブ化、その他の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="0101f-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="0101f-141">ルールを適用する前に、ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0101f-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="0101f-142">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0101f-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="0101f-143">PowerShell を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="0101f-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="0101f-144">この例では、この記事で説明する方法を使用して Microsoft に報告される電子メール メッセージを参照する、BCC Messages Reported to Microsoft という名前の新しいメール フロー ルールを作成し、ユーザー laura@contoso.com と julia@contoso.com を BCC 受信者として追加します。</span><span class="sxs-lookup"><span data-stu-id="0101f-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="0101f-145">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0101f-145">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0101f-146">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0101f-146">How do you know this worked?</span></span>

<span data-ttu-id="0101f-147">報告されたメッセージのコピーを受信するようにメール フロー ルールが構成されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0101f-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="0101f-148">EAC で、メール フロー ルールに **移動** し、ルールを選択して編集アイコンをクリックし、 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0101f-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="0101f-149">PowerShell で、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0101f-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="0101f-150">レポート電子メール アドレスの 1 つにテスト メッセージを送信し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="0101f-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
