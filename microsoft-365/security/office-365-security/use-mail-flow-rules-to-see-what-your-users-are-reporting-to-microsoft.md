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
ms.openlocfilehash: 34857c368fc910eeb43f6a78c490b9ad7568db1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918632"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="ce638-103">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="ce638-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ce638-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ce638-104">**Applies to**</span></span>
- [<span data-ttu-id="ce638-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ce638-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ce638-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ce638-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ce638-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce638-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ce638-108">Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、「メッセージと[](report-junk-email-messages-to-microsoft.md)ファイルを Microsoft に報告する」で説明したように、ユーザーが分析のために Microsoft にメッセージを報告する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="ce638-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="ce638-109">ユーザーが Microsoft に報告するメッセージを探すメール フロー ルール (トランスポート ルールとも呼ばれる) を作成し、これらの報告されたメッセージのコピーを受信する BCC 受信者を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ce638-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="ce638-110">メール フロー ルールは、Exchange 管理センター (EAC) と PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) に作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce638-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ce638-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ce638-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ce638-112">この記事の手順を実行するには、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce638-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="ce638-113">具体的には、既定では、組織の管理、コンプライアンス管理 **(グローバル** 管理者)、レコード管理の役割グループに割り当てられているトランスポート ルールの役割が必要です。 </span><span class="sxs-lookup"><span data-stu-id="ce638-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="ce638-114">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce638-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="ce638-115">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ce638-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="ce638-116">スタンドアロン EOP のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ce638-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="ce638-117">役割グループ内のメンバーの一覧を変更する EAC を使用する</span><span class="sxs-lookup"><span data-stu-id="ce638-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="ce638-118">Exchange Online で EAC を開く方法については、「Exchange Online [の Exchange 管理センター」を参照してください](/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="ce638-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="ce638-119">スタンドアロン EOP で EAC を開く方法については、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ce638-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ce638-120">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce638-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ce638-121">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce638-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ce638-122">Exchange Online およびスタンドアロン EOP のメール フロー ルールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce638-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="ce638-123">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="ce638-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="ce638-124">Exchange Online のメール フロー ルールでの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="ce638-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="ce638-125">Exchange Online でのメール フロー ルールの処理</span><span class="sxs-lookup"><span data-stu-id="ce638-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ce638-126">EAC を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="ce638-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="ce638-127">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce638-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ce638-128">[追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルール **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce638-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ce638-129">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="ce638-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ce638-130">**名前**: ルールの一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce638-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="ce638-131">たとえば、BCC メッセージが Microsoft に報告されました。</span><span class="sxs-lookup"><span data-stu-id="ce638-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="ce638-132">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce638-132">Click **More Options**.</span></span>

   - <span data-ttu-id="ce638-133">[受信者アドレスに次のいずれかの単語が含まれる] を選択する場合は、次のルールを適用します。表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[アイコンの追加] をクリックし、すべての値を入力するまで繰り返します。 \>    ![ ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="ce638-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="ce638-134">エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="ce638-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ce638-135">エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="ce638-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="ce638-136">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce638-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="ce638-137">**[Bcc] ボックス** に **[受信者を追加** \> **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce638-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="ce638-138">表示されるダイアログで、追加する受信者を見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="ce638-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="ce638-139">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce638-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="ce638-140">追加の選択を行って、ルールの監査、ルールのテスト、特定の期間中のルールのアクティブ化、その他の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="ce638-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="ce638-141">ルールを適用する前に、ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ce638-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="ce638-142">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce638-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ce638-143">PowerShell を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="ce638-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="ce638-144">この例では、この記事で説明するメソッドを使用して Microsoft に報告される電子メール メッセージを確認し、ユーザー laura@contoso.com および julia@contoso.com を BCC 受信者として追加する、Bcc Messages Reported to Microsoft という名前の新しいメール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce638-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="ce638-145">詳細な構文とパラメーターについては、「[New-TransportRule](/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce638-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ce638-146">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="ce638-146">How do you know this worked?</span></span>

<span data-ttu-id="ce638-147">報告されたメッセージのコピーを受信するようにメール フロー ルールが構成されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ce638-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="ce638-148">EAC で、[メールフロールール] に移動し、[編集] アイコンをクリックして、 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce638-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="ce638-149">PowerShell で、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce638-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="ce638-150">レポート電子メール アドレスの 1 つにテスト メッセージを送信し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce638-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>