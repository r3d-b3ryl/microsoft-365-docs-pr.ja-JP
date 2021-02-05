---
title: Advanced Message Encryption によって暗号化された電子メールを取り消す
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
description: 管理者として、またメッセージ送信者として、365 Advanced Message Encryption で暗号化された特定のメールOffice取り消しできます。
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105142"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="00b8a-103">Advanced Message Encryption によって暗号化された電子メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="00b8a-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="00b8a-104">電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="00b8a-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="00b8a-105">Office 365 Advanced Message Encryption は [、Microsoft 365 Enterprise E5、Office](https://www.microsoft.com/microsoft-365/enterprise/home)365 E5、Microsoft 365 E5 (Nonprofit Staff Pricing)、Office 365 Enterprise E5 (Nonprofit Staff Pricing)、および Office 365 Education A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="00b8a-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="00b8a-106">組織に 365 Advanced Message Encryption Office含めないサブスクリプションがある場合、 Microsoft 365 E3 用の Microsoft 365 E5 コンプライアンス SKU アドオン、Microsoft 365 E3 (Nonprofit Staff Pricing)、または microsoft 365 E3、Microsoft 365 E3 (Nonprofit Staff Pricing)、または Office 365 Advanced Compliance SKU アドオン、または Office 365 SKU で購入できます。</span><span class="sxs-lookup"><span data-stu-id="00b8a-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="00b8a-107">この記事は、Office [365 Message Encryption](ome.md)に関する大規模な一連の記事の一部です。</span><span class="sxs-lookup"><span data-stu-id="00b8a-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="00b8a-108">Office 365 Advanced Message Encryption を使用してメッセージが暗号化され、Microsoft 365 管理者またはメッセージの送信者である場合は、特定の条件下でメッセージを取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00b8a-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="00b8a-109">管理者は PowerShell を使用してメッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="00b8a-110">送信者は、Outlook on the web から直接送信したメッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="00b8a-111">この記事では、失効が可能な状況と取り消し方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="00b8a-112">取り消し可能な暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="00b8a-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="00b8a-113">管理者とメッセージ送信者は、受信者がリンクベースのブランド化された暗号化された電子メールを受信した場合、暗号化された電子メールを取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00b8a-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="00b8a-114">受信者がサポートされている Outlook クライアントでネイティブインライン エクスペリエンスを受信した場合、メッセージを取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="00b8a-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="00b8a-115">受信者がリンク ベースのエクスペリエンスとインライン エクスペリエンスのどちらのエクスペリエンスを受け取るかどうかは、受信者 ID の種類によって異なります。Office 365 と Microsoft アカウントの受信者 (outlook.com ユーザーなど) は、サポートされている Outlook クライアントでインライン エクスペリエンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="00b8a-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="00b8a-116">Gmail や Yahoo の受信者など、他のすべての受信者の種類には、リンク ベースのエクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="00b8a-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="00b8a-117">管理者とメッセージ送信者は、Outlook on the web から直接適用された暗号化を使用して暗号化されたメッセージを取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00b8a-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="00b8a-118">たとえば、[暗号化のみ] オプションを使用して暗号化されたメッセージなどです。</span><span class="sxs-lookup"><span data-stu-id="00b8a-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Outlook on the web の [暗号化のみ] オプションを示すスクリーンショット。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="00b8a-120">失効した暗号化されたメールの受信者エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="00b8a-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="00b8a-121">電子メールが失効すると、受信者は Office 365 Message Encryption ポータルを通じて暗号化された電子メールにアクセスすると、「メッセージは送信者によって取り消されました」というエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="00b8a-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![失効した暗号化された電子メールを示すスクリーンショット。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="00b8a-123">送信した暗号化されたメッセージを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="00b8a-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="00b8a-124">1 人の受信者に送信したメールを取り消し、その受信者がソーシャル アカウント (gmail.com や yahoo.com など) を使用yahoo.com。</span><span class="sxs-lookup"><span data-stu-id="00b8a-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="00b8a-125">つまり、リンク ベースのエクスペリエンスを受け取った 1 人の受信者に送信された電子メールを取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00b8a-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="00b8a-126">Office 365 または Microsoft 365 の仕事または学校のアカウントを使用する受信者、または microsoft アカウントを使用するユーザー (outlook.com アカウントなど) に送信したメールを取り消しすることはできません。</span><span class="sxs-lookup"><span data-stu-id="00b8a-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="00b8a-127">送信した暗号化されたメッセージを取り消す場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="00b8a-128">Outlook on the web の **送信** フォルダーで、取り消すメッセージを参照します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="00b8a-129">メールが取り消し可能な場合は、メッセージの上部に [外部アクセスの削除] リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00b8a-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Outlook on the web で取り消す暗号化されたメールを示すスクリーンショット。":::

2. <span data-ttu-id="00b8a-131">[外部 **アクセスの削除] をクリック** してメッセージを取り消します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="00b8a-132">メッセージは、その状態が取り消された状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="00b8a-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Outlook on the web で取り消された暗号化されたメッセージを示すスクリーンショット。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="00b8a-134">管理者として暗号化されたメッセージを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="00b8a-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="00b8a-135">Microsoft 365 管理者は、次の一般的な手順に従って、有効な暗号化された電子メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="00b8a-136">電子メールのメッセージ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="00b8a-137">メッセージを取り消し可能な場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="00b8a-138">メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="00b8a-139">手順 1.</span><span class="sxs-lookup"><span data-stu-id="00b8a-139">Step 1.</span></span> <span data-ttu-id="00b8a-140">電子メールのメッセージ ID を取得する</span><span class="sxs-lookup"><span data-stu-id="00b8a-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="00b8a-141">暗号化されたメールを取り消す前に、メールのメッセージ ID を収集します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="00b8a-142">通常、MessageId の形式は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="00b8a-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="00b8a-143">取り消す電子メールのメッセージ ID を検索する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="00b8a-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="00b8a-144">このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="00b8a-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="00b8a-145">セキュリティ コンプライアンス センターでメッセージ追跡を使用して、取り消す電子メールのメッセージ ID を &amp; 識別するには</span><span class="sxs-lookup"><span data-stu-id="00b8a-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="00b8a-146">セキュリティ/コンプライアンス センターで新しいメッセージ追跡を使用して、送信者または受信者& [検索します](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)。</span><span class="sxs-lookup"><span data-stu-id="00b8a-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="00b8a-147">メールを見つから選択すると、[メッセージ追跡の詳細] ウィンドウ **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="00b8a-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="00b8a-148">[ **詳細] を展開** してメッセージ ID を見つける。</span><span class="sxs-lookup"><span data-stu-id="00b8a-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="00b8a-149">セキュリティ コンプライアンス センターのメッセージ暗号化レポートを使用してOfficeのメッセージ ID を &amp; 特定するには</span><span class="sxs-lookup"><span data-stu-id="00b8a-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="00b8a-150">セキュリティ コンプライアンス センター &amp; で、メッセージ暗号化レポート **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="00b8a-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="00b8a-151">このレポートの詳細については、セキュリティ コンプライアンス センター [でメール セキュリティ レポートを表示するを &amp; 参照してください](../security/office-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="00b8a-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="00b8a-152">[詳細 **の表示] テーブル** を選択し、取り消すメッセージを特定します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="00b8a-153">メッセージ ID を含む詳細を表示するには、メッセージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="00b8a-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="00b8a-154">手順 2.</span><span class="sxs-lookup"><span data-stu-id="00b8a-154">Step 2.</span></span> <span data-ttu-id="00b8a-155">メールが取り消し可能な場合の確認</span><span class="sxs-lookup"><span data-stu-id="00b8a-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="00b8a-156">メッセージを取り消すかどうかを確認するには、セキュリティ コンプライアンス センターの [詳細] テーブルで、失効状態フィールドが暗号化レポートに表示されているかどうかを &amp; 確認します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="00b8a-157">メール メッセージを使用して特定の電子メール メッセージを取り消Windows PowerShell、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="00b8a-158">組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00b8a-159">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00b8a-159">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00b8a-160">次のようにGet-OMEMessageStatusコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="00b8a-161">このコマンドは、メッセージの件名と、メッセージが取り消し可能かどうかを返します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="00b8a-162">例えば、</span><span class="sxs-lookup"><span data-stu-id="00b8a-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="00b8a-163">手順 3.</span><span class="sxs-lookup"><span data-stu-id="00b8a-163">Step 3.</span></span> <span data-ttu-id="00b8a-164">メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="00b8a-164">Revoke the mail</span></span>

<span data-ttu-id="00b8a-165">取り消す電子メールのメッセージ ID を確認し、メッセージが取り消し可能なと確認したら、セキュリティ コンプライアンス センターまたは Windows PowerShell を使用して電子メールを取り消 &amp; します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="00b8a-166">セキュリティ コンプライアンス センターを使用してメッセージを &amp; 取り消す方法</span><span class="sxs-lookup"><span data-stu-id="00b8a-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="00b8a-167">組織のグローバル管理者のアクセス許可を持つ、仕事または学校のアカウントを使用して、セキュリティ/コンプライアンス センター&接続します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="00b8a-168">暗号化レポート **のメッセージの** 詳細テーブル **で** 、[メッセージの取り消し **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="00b8a-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="00b8a-169">電子メール を使用して電子メールを取りWindows PowerShell、次のコマンドレットSet-OMEMessageRevocationします。</span><span class="sxs-lookup"><span data-stu-id="00b8a-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="00b8a-170">組織でグローバル管理者のアクセス許可を持つ、仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="00b8a-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00b8a-171">次のようにSet-OMEMessageRevocationコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="00b8a-172">電子メールが取り消されたかどうかを確認するには、次Get-OMEMessageStatusコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="00b8a-173">失効が成功した場合、コマンドレットは次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="00b8a-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="00b8a-174">365 Advanced Message Encryption Officeの詳細</span><span class="sxs-lookup"><span data-stu-id="00b8a-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="00b8a-175">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="00b8a-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="00b8a-176">Office 365 Advanced Message Encryption - 電子メールの有効期限</span><span class="sxs-lookup"><span data-stu-id="00b8a-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="00b8a-177">メッセージ ポリシーとコンプライアンス サービスの説明</span><span class="sxs-lookup"><span data-stu-id="00b8a-177">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
