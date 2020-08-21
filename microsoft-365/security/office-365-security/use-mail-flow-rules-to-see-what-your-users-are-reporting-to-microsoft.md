---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理者は、メール フロー ルール (別名トランスポート ルール) を使用して、ユーザーが Microsoft に報告するメッセージのコピーを受信する方法について学習できます。
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827387"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="caff2-103">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="caff2-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="caff2-104">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、メッセージの報告とファイルについての説明の説明のとおりに、ユーザーが分析のため Microsoft [にメッセージを報告する方法が複数あります](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="caff2-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="caff2-105">ユーザーが Microsoft に報告するメッセージを検索するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成し、報告されたメッセージのコピーを受信するように BCC 受信者を構成できます。</span><span class="sxs-lookup"><span data-stu-id="caff2-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="caff2-106">メール フロー ルールは、Exchange 管理センター (EAC) と PowerShell (Exchange Online にメールボックスが置かれており、Exchange Online メールボックスを持つ組織用のスタンドアロン EOP PowerShell) で作成できます。</span><span class="sxs-lookup"><span data-stu-id="caff2-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="caff2-107">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="caff2-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="caff2-108">これらの手順を実行する前に、Exchange Online または EOP でアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="caff2-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="caff2-109">特に、組織管理、コンプライアンス管理、**およびレコード**管理の各役割に既定で**Organization Management**割り当てられる **、** トランスポート ルールの**役割を割り**当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="caff2-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="caff2-110">詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff2-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="caff2-111">EAC を開くには[、「Exchange Online の Exchange 管理センター」または](https://docs.microsoft.com/Exchange/exchange-admin-center)[「スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="caff2-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="caff2-112">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff2-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="caff2-113">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff2-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="caff2-114">Exchange Online でのメール フロー ルールとスタンドアロン EOP のメール フロー ルールの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff2-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="caff2-115">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="caff2-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="caff2-116">Exchange Online のメール フロー ルールでの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="caff2-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="caff2-117">Exchange Online でのメール フロー ルールの処理</span><span class="sxs-lookup"><span data-stu-id="caff2-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="caff2-118">EAC を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="caff2-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="caff2-119">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="caff2-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="caff2-120">[追加 **] アイコン** ![ をクリック ](../../media/ITPro-EAC-AddIcon.png) し、[新しい **ルールを作成する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="caff2-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="caff2-121">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="caff2-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="caff2-122">**名前**: わかりやすい一意のルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="caff2-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="caff2-123">たとえば、Bcc メッセージは Microsoft に報告されます。</span><span class="sxs-lookup"><span data-stu-id="caff2-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="caff2-124">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caff2-124">Click **More Options**.</span></span>

   - <span data-ttu-id="caff2-125">**受信者のアドレスに次**のいずれかの単語**が**含まれている場合に、このルール \> **を適用します**。表示**される単語**または語句を指定します。ダイアログで、次の値のいずれかを**Add**入力して [ ![ 追加] アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) し、すべての値を入力するまで繰り返します。</span><span class="sxs-lookup"><span data-stu-id="caff2-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="caff2-126">エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="caff2-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="caff2-127">エントリを削除するには、エントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="caff2-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="caff2-128">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caff2-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="caff2-129">**次の手順に**従います。[ **受信者を** \> **BCC ボックスに追加する] を選います**。</span><span class="sxs-lookup"><span data-stu-id="caff2-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="caff2-130">表示されるダイアログで、追加する受信者を見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="caff2-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="caff2-131">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caff2-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="caff2-132">ルールを監査する、ルールをテストする、一定期間内にルールをアクティブ化する、その他の設定など、追加を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="caff2-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="caff2-133">ルールを適用する前に、ルールをテストしてみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="caff2-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="caff2-134">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="caff2-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="caff2-135">PowerShell を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="caff2-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="caff2-136">この例では、Bcc Messages Reported という名前の新しいメール フロー ルールを作成して、このトピックで説明した方法を使用して Microsoft に報告されたメール メッセージを検索し、ユーザー laura@contoso.com および julia@contoso.com を BCC 受信者として追加します。</span><span class="sxs-lookup"><span data-stu-id="caff2-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="caff2-137">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff2-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="caff2-138">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="caff2-138">How do you know this worked?</span></span>

<span data-ttu-id="caff2-139">報告されたメッセージのコピーを受信するようにメール フロー ルールが構成されていることを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="caff2-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="caff2-140">EAC で、[メール フロー ルール]**に移動し** \> **Rules** \> 、[編集] アイコン \> をクリック**Edit** ![ して ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="caff2-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="caff2-141">PowerShell で次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="caff2-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="caff2-142">テスト メッセージをレポートのメール アドレスのいずれかに送信し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="caff2-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
