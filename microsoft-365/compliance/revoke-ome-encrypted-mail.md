---
title: 高度なメッセージ暗号化で暗号化された電子メールを取り消す
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 管理者およびメッセージ送信者として、Office 365 Advanced Message Encryption で暗号化された特定の電子メールを取り消すことができます。
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868952"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="c77bc-103">高度なメッセージ暗号化で暗号化された電子メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="c77bc-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="c77bc-104">電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="c77bc-105">Office 365 の高度なメッセージの暗号化は、 [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体の価格)、Office 365 Enterprise E5 (非営利スタッフの価格)、office の365教育用 A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c77bc-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="c77bc-106">Office 365 Advanced Message Encryption が含まれていないサブスクリプションが組織にある場合は、microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Office の 365 Sku で、Microsoft 365 E5 コンプライアンス SKU アドオンを使用して購入できます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="c77bc-107">この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。</span><span class="sxs-lookup"><span data-stu-id="c77bc-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="c77bc-108">Office 365 Advanced Message Encryption を使用してメッセージが暗号化されていて、Microsoft 365 管理者またはメッセージの送信者である場合は、特定の条件下でメッセージを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="c77bc-109">管理者が PowerShell を使用してメッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="c77bc-110">送信者は、Outlook on the web から直接送信したメッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="c77bc-111">この記事では、失効が可能な状況とその方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="c77bc-112">取り消すことができる暗号化された電子メール</span><span class="sxs-lookup"><span data-stu-id="c77bc-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="c77bc-113">管理者およびメッセージの送信者が、リンクベースの、ブランド化された電子メールを受信した場合、暗号化された電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="c77bc-114">受信者が、サポートされている Outlook クライアントでネイティブインライン環境を受信した場合、メッセージを取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="c77bc-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="c77bc-115">受信者がリンクベースの機能を受信するか、またはインラインでの使用を許可するかは、受信者の id の種類によって異なります。 Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com users) は、サポートされている Outlook クライアントでインラインの動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="c77bc-116">Gmail、Yahoo 受信者など、他のすべての受信者の種類は、リンクベースの処理を行います。</span><span class="sxs-lookup"><span data-stu-id="c77bc-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="c77bc-117">管理者およびメッセージ送信者は、Outlook on the web から直接適用される暗号化を使用して暗号化されたメッセージを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="c77bc-118">たとえば、[暗号化のみ] オプションで暗号化されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="c77bc-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Outlook on the web の [暗号化のみ] オプションを示すスクリーンショット。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="c77bc-120">取り消された暗号化された電子メールの受信者向けの手順</span><span class="sxs-lookup"><span data-stu-id="c77bc-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="c77bc-121">電子メールが失効されると、受信者は Office 365 メッセージ暗号化ポータルを経由して暗号化された電子メールにアクセスしたときにエラーを受信します。 "メッセージは送信者によって取り消されました"。</span><span class="sxs-lookup"><span data-stu-id="c77bc-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![取り消された暗号化された電子メールを示すスクリーンショット。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="c77bc-123">送信した暗号化されたメッセージを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="c77bc-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="c77bc-124">送信した暗号化されたメッセージを取り消すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="c77bc-125">Web 上の Outlook の [ **送信済みアイテム** ] フォルダーで、取り消したいメッセージを参照します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="c77bc-126">メールが revocable の場合は、メッセージの上部にある [外部アクセスの削除] リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Outlook on the web で取り消したい暗号化されたメールを示すスクリーンショット。":::

2. <span data-ttu-id="c77bc-128">[ **外部アクセスの削除** ] をクリックして、メッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="c77bc-129">メッセージは、状態が [失効済みであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c77bc-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Outlook on the web で暗号化されたメッセージが取り消されたことを示すスクリーンショット。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="c77bc-131">暗号化されたメッセージを管理者として取り消す方法</span><span class="sxs-lookup"><span data-stu-id="c77bc-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="c77bc-132">Microsoft 365 管理者は、次の一般的な手順に従って、対象となる暗号化された電子メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="c77bc-133">電子メールのメッセージ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="c77bc-134">メッセージを取り消すことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="c77bc-135">メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="c77bc-136">手順 1.</span><span class="sxs-lookup"><span data-stu-id="c77bc-136">Step 1.</span></span> <span data-ttu-id="c77bc-137">電子メールのメッセージ ID を取得する</span><span class="sxs-lookup"><span data-stu-id="c77bc-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="c77bc-138">暗号化されたメールを取り消すには、メールのメッセージ ID を収集します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="c77bc-139">MessageId は通常、次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="c77bc-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="c77bc-140">取り消したい電子メールのメッセージ ID を複数の方法で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="c77bc-141">このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="c77bc-142">セキュリティ/コンプライアンスセンターのメッセージ追跡を使用して取り消す電子メールのメッセージ ID を特定するには &amp;</span><span class="sxs-lookup"><span data-stu-id="c77bc-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="c77bc-143">[セキュリティ & コンプライアンスセンターで、新しいメッセージの追跡](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者によって電子メールを検索します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="c77bc-144">電子メールを見つけたら、それを選択して **メッセージ追跡の詳細** ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="c77bc-145">**詳細情報**を展開して、メッセージ ID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="c77bc-146">セキュリティ/コンプライアンスセンターで Office メッセージの暗号化レポートを使用して取り消す電子メールのメッセージ ID を特定するには &amp;</span><span class="sxs-lookup"><span data-stu-id="c77bc-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="c77bc-147">セキュリティ &amp; /コンプライアンスセンターで、[メッセージの **暗号化] レポート**に移動します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="c77bc-148">このレポートの詳細については、「 [セキュリティ &amp; センターのコンプライアンスセンターで電子メールのセキュリティレポートを表示する](../security/office-365-security/view-email-security-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c77bc-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="c77bc-149">[ **詳細の表示** ] テーブルを選択し、取り消すメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="c77bc-150">メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="c77bc-151">手順 2。</span><span class="sxs-lookup"><span data-stu-id="c77bc-151">Step 2.</span></span> <span data-ttu-id="c77bc-152">メールが revocable かどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="c77bc-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="c77bc-153">メッセージを取り消すことができるかどうかを確認するには、セキュリティコンプライアンスセンターの **詳細** 表で、[失効状態] フィールドが [暗号化] レポートに表示されているかどうかを確認し &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="c77bc-154">Windows PowerShell を使用して特定の電子メールメッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="c77bc-155">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c77bc-156">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c77bc-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c77bc-157">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="c77bc-158">このコマンドは、メッセージの件名と、メッセージが revocable であるかどうかを返します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="c77bc-159">例えば、</span><span class="sxs-lookup"><span data-stu-id="c77bc-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="c77bc-160">手順 3.</span><span class="sxs-lookup"><span data-stu-id="c77bc-160">Step 3.</span></span> <span data-ttu-id="c77bc-161">メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="c77bc-161">Revoke the mail</span></span>

<span data-ttu-id="c77bc-162">取り消したい電子メールのメッセージ ID がわかっていて、そのメッセージが revocable であることを確認したら、セキュリティ &amp; コンプライアンスセンターまたは Windows PowerShell を使用して電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="c77bc-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="c77bc-163">セキュリティ/コンプライアンスセンターを使用してメッセージを取り消すには &amp;</span><span class="sxs-lookup"><span data-stu-id="c77bc-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="c77bc-164">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、セキュリティ & コンプライアンスセンターに接続します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="c77bc-165">[ **暗号化レポート**] の [メッセージの **詳細** ] テーブルで、[ **メッセージの取り消し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="c77bc-166">Windows PowerShell を使用して電子メールを失効させるには、OMEMessageRevocation コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="c77bc-167">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://aka.ms/exopowershell)します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c77bc-168">OMEMessageRevocation コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="c77bc-169">電子メールが失効したかどうかを確認するには、次のようにして、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="c77bc-170">失効が成功した場合、コマンドレットは次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="c77bc-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="c77bc-171">Office 365 の詳細なメッセージの暗号化に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="c77bc-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="c77bc-172">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="c77bc-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="c77bc-173">Office 365 の高度なメッセージの暗号化-電子メールの有効期限</span><span class="sxs-lookup"><span data-stu-id="c77bc-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="c77bc-174">メッセージポリシーとコンプライアンスサービスの説明</span><span class="sxs-lookup"><span data-stu-id="c77bc-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
