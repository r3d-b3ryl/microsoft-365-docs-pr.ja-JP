---
title: 高度なメッセージ暗号化によって暗号化された電子メールを取り消す
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
description: 管理者として、およびメッセージ送信者として、ユーザーが暗号化された特定の電子メールを取り消Office 365 Advanced Message Encryption。
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051719"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="e4ac3-103">高度なメッセージ暗号化によって暗号化された電子メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="e4ac3-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="e4ac3-104">電子メールの失効は、電子メールの一部Office 365 Advanced Message Encryption。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="e4ac3-105">Office 365 Advanced Message Encryptionは[、Microsoft 365 Enterprise E5、Office 365](https://www.microsoft.com/microsoft-365/enterprise/home)E5、Microsoft 365 E5 (非営利スタッフ価格)、Office 365 Enterprise E5 (非営利スタッフ価格)、および Office 365 Education A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="e4ac3-106">組織に Office 365 Advanced Message Encryption を含めないサブスクリプションがある場合は、Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格) の Microsoft 365 E5 Compliance SKU アドオン、または Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Office 365 SKU の Office 365 Advanced Compliance SKU アドオンを使用して購入できます。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="e4ac3-107">この記事は、この記事に関する一連の[記事の一](ome.md)部Office 365 Message Encryption。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="e4ac3-108">Office 365 Advanced Message Encryption を使用してメッセージが暗号化され、Microsoft 365 管理者である場合、またはメッセージの送信者である場合は、特定の条件下でメッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="e4ac3-109">管理者は PowerShell を使用してメッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="e4ac3-110">送信者として、Web 上のユーザーから直接送信したOutlook取り消します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="e4ac3-111">この記事では、失効が可能な状況と取り消し方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="e4ac3-112">取り消し可能な暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="e4ac3-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="e4ac3-113">受信者がリンクベースのブランド化された暗号化メールを受信した場合、管理者とメッセージ送信者は暗号化された電子メールを取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="e4ac3-114">受信者がサポートされているクライアントでネイティブ インライン エクスペリエンスをOutlook場合、メッセージを取り消す事はできません。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="e4ac3-115">受信者がリンク ベースのエクスペリエンスまたはインライン エクスペリエンスを受け取るかどうかは、受信者 ID の種類によって異なります。Office 365 および Microsoft アカウントの受信者 (outlook.com ユーザーなど) は、サポートされている Outlook クライアントでインライン エクスペリエンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="e4ac3-116">Gmail や Yahoo 受信者などの他のすべての受信者の種類は、リンク ベースのエクスペリエンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="e4ac3-117">管理者とメッセージ送信者は、Web 上のユーザーから直接適用された暗号化を使用して暗号化されたOutlook取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="e4ac3-118">たとえば、[暗号化のみ] オプションで暗号化されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Web 上の [暗号化のみ] オプションをOutlookスクリーンショット。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="e4ac3-120">失効した暗号化された電子メールの受信者エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e4ac3-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="e4ac3-121">電子メールが取り消された後、受信者は Office 365 Message Encryption ポータルを介して暗号化された電子メールにアクセスするときにエラーを受け取ります。"メッセージは送信者によって取り消されました"。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![失効した暗号化された電子メールを示すスクリーンショット。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="e4ac3-123">送信した暗号化されたメッセージを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="e4ac3-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="e4ac3-124">1 人の受信者に送信したメールを取り消して、ソーシャル アカウントを使用 gmail.com、yahoo.com。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="e4ac3-125">つまり、リンク ベースのエクスペリエンスを受け取った 1 人の受信者に送信された電子メールを取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="e4ac3-126">Office 365 または Microsoft 365 の仕事または学校のアカウントを使用する受信者、または Microsoft アカウントを使用するユーザー (outlook.com アカウントなど) に送信したメールを取り消 outlook.com できません。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="e4ac3-127">送信した暗号化されたメッセージを取り消す場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="e4ac3-128">Web Outlook送信フォルダーで、取り消すメッセージを参照します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="e4ac3-129">メールが失効可能な場合は、メッセージの上部に [外部アクセスの削除] リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Web 上で無効にしたい暗号化されたメールを示Outlookスクリーンショット。":::

2. <span data-ttu-id="e4ac3-131">[外部 **アクセスの削除] をクリック** して、メッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="e4ac3-132">メッセージは、その状態が取り消された状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Web 上で無効にされた暗号化されたメッセージOutlook示すスクリーンショット。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="e4ac3-134">管理者として暗号化されたメッセージを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="e4ac3-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="e4ac3-135">Microsoft 365管理者は、次の一般的な手順に従って、適格な暗号化された電子メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="e4ac3-136">電子メールのメッセージ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="e4ac3-137">メッセージを取り消す可能性を確認します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="e4ac3-138">メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="e4ac3-139">手順 1.</span><span class="sxs-lookup"><span data-stu-id="e4ac3-139">Step 1.</span></span> <span data-ttu-id="e4ac3-140">電子メールのメッセージ ID を取得する</span><span class="sxs-lookup"><span data-stu-id="e4ac3-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="e4ac3-141">暗号化されたメールを取り消す前に、メールのメッセージ ID を収集します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="e4ac3-142">MessageId は通常、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="e4ac3-143">取り消す電子メールのメッセージ ID を検索する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="e4ac3-144">このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="e4ac3-145">セキュリティ コンプライアンス センターでメッセージ トレースを使用して取り消す電子メールのメッセージ ID を &amp; 識別するには</span><span class="sxs-lookup"><span data-stu-id="e4ac3-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="e4ac3-146">[セキュリティ] コンプライアンス センターの [新しいメッセージ トレース] を使用して、送信者 [または受信者&検索します](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="e4ac3-147">電子メールを見つから選択すると、[メッセージ 追跡の詳細] **ウィンドウが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="e4ac3-148">[詳細 **] を展開** してメッセージ ID を探します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="e4ac3-149">セキュリティ コンプライアンス センターの [メッセージ暗号化] レポートを使用してOfficeのメッセージ ID を &amp; 識別するには</span><span class="sxs-lookup"><span data-stu-id="e4ac3-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="e4ac3-150">セキュリティ コンプライアンス センター &amp; で、[メッセージの暗号化] **レポートに移動します**。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="e4ac3-151">このレポートの詳細については、「セキュリティ コンプライアンス センター [で電子メール セキュリティ レポートを表示する」を &amp; 参照してください](../security/defender-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="e4ac3-152">[詳細の **表示] テーブル** を選択し、取り消すメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="e4ac3-153">メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="e4ac3-154">手順 2.</span><span class="sxs-lookup"><span data-stu-id="e4ac3-154">Step 2.</span></span> <span data-ttu-id="e4ac3-155">メールが失効可能な場合の確認</span><span class="sxs-lookup"><span data-stu-id="e4ac3-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="e4ac3-156">メッセージを取り消すかどうかを確認するには、セキュリティ コンプライアンス センターの [詳細] テーブルの [暗号化]レポートに [失効の状態] フィールドが表示されているかどうかを &amp; 確認します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="e4ac3-157">メール メッセージを使用して特定の電子メール メッセージを取り消Windows PowerShell、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="e4ac3-158">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e4ac3-159">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e4ac3-160">次のようにGet-OMEMessageStatusコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="e4ac3-161">このコマンドは、メッセージの件名とメッセージが取り消し可能かどうかを返します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="e4ac3-162">例えば、</span><span class="sxs-lookup"><span data-stu-id="e4ac3-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="e4ac3-163">手順 3.</span><span class="sxs-lookup"><span data-stu-id="e4ac3-163">Step 3.</span></span> <span data-ttu-id="e4ac3-164">メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="e4ac3-164">Revoke the mail</span></span>

<span data-ttu-id="e4ac3-165">取り消す電子メールのメッセージ ID がわかり、メッセージが失効可能かどうか確認したら、セキュリティ コンプライアンス センターまたは Windows PowerShell を使用して電子 &amp; メールを取り消Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="e4ac3-166">セキュリティ コンプライアンス センターを使用してメッセージを &amp; 取り消す方法</span><span class="sxs-lookup"><span data-stu-id="e4ac3-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="e4ac3-167">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、コンプライアンス センターのセキュリティ &接続します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="e4ac3-168">[暗号化] **レポートの** メッセージの [ **詳細]** テーブルで、[メッセージの取り消し] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="e4ac3-169">メールを使用してメールを取り消Windows PowerShell、Set-OMEMessageRevocationします。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="e4ac3-170">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)ConnectをExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e4ac3-171">次のようにSet-OMEMessageRevocationコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="e4ac3-172">電子メールが取り消されたかどうかを確認するには、次のように Get-OMEMessageStatusコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="e4ac3-173">失効が成功した場合、コマンドレットは次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="e4ac3-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="e4ac3-174">詳細については、Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="e4ac3-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="e4ac3-175">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="e4ac3-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="e4ac3-176">Office 365 Advanced Message Encryption - メールの有効期限</span><span class="sxs-lookup"><span data-stu-id="e4ac3-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="e4ac3-177">メッセージ ポリシーとコンプライアンス サービスの説明</span><span class="sxs-lookup"><span data-stu-id="e4ac3-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)