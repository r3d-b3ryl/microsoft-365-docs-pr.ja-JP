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
ms.date: 02/28/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 管理者は、Office 365 Advanced Message Encryption で暗号化された特定の電子メールを取り消すことができます。
ms.openlocfilehash: 271aa1b3644983907c341cf7f9ad6d526597ad59
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626493"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="f06f4-103">高度なメッセージ暗号化で暗号化された電子メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="f06f4-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="f06f4-104">電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="f06f4-105">Office 365 の高度なメッセージの暗号化は、 [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体の価格)、Office 365 Enterprise E5 (非営利スタッフの価格)、office の365教育用 A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f06f4-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="f06f4-106">Office 365 Advanced Message Encryption が含まれていないサブスクリプションが組織にある場合は、microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Office の 365 Sku で、Microsoft 365 E5 コンプライアンス SKU アドオンを使用して購入できます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="f06f4-107">この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。</span><span class="sxs-lookup"><span data-stu-id="f06f4-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="f06f4-108">Office 365 Advanced Message Encryption を使用してメッセージが暗号化されていて、Microsoft 365 管理者である場合は、特定の条件下でメッセージを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="f06f4-109">この記事では、失効が可能な状況とその方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="f06f4-110">取り消すことができる暗号化された電子メール</span><span class="sxs-lookup"><span data-stu-id="f06f4-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="f06f4-111">受信者がリンクベースの、ブランド化された電子メールを受信した場合は、暗号化された電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="f06f4-112">受信者が、サポートされている Outlook クライアントでネイティブインライン環境を受信した場合は、それらを取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f06f4-112">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke those.</span></span>

<span data-ttu-id="f06f4-113">受信者がリンクベースの機能を受信するか、またはインラインでの使用を許可するかは、受信者の id の種類によって異なります。 Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com users) は、サポートされている Outlook クライアントでインラインの動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="f06f4-114">Gmail 受信者など、他のすべての受信者の種類は、リンクベースの処理を行います。</span><span class="sxs-lookup"><span data-stu-id="f06f4-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="f06f4-115">取り消された暗号化された電子メールの受信者向けの手順</span><span class="sxs-lookup"><span data-stu-id="f06f4-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="f06f4-116">電子メールが失効されると、受信者は Office 365 メッセージ暗号化ポータルを経由して暗号化された電子メールにアクセスしたときにエラーを受信します。 "メッセージは送信者によって取り消されました"。</span><span class="sxs-lookup"><span data-stu-id="f06f4-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![取り消された暗号化された電子メールを示すスクリーンショット。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="f06f4-118">暗号化された電子メールを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="f06f4-118">How to revoke an encrypted email</span></span>

<span data-ttu-id="f06f4-119">Microsoft 365 管理者は、次の一般的な手順に従って、対象となる暗号化された電子メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-119">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="f06f4-120">電子メールのメッセージ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-120">Get the Message ID of the email.</span></span>
- <span data-ttu-id="f06f4-121">メッセージを取り消すことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-121">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="f06f4-122">メールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-122">Revoke the mail.</span></span>

<span data-ttu-id="f06f4-123">失効プロセスの各手順の詳細な手順については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f06f4-123">Keep reading for in-depth instructions for each step in the revocation process.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="f06f4-124">手順 1. </span><span class="sxs-lookup"><span data-stu-id="f06f4-124">Step 1.</span></span> <span data-ttu-id="f06f4-125">電子メールのメッセージ ID を取得する</span><span class="sxs-lookup"><span data-stu-id="f06f4-125">Obtain the Message ID of the email</span></span>

<span data-ttu-id="f06f4-126">暗号化されたメールを取り消すには、メールのメッセージ ID を収集します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-126">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="f06f4-127">MessageId は通常、次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="f06f4-127">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="f06f4-128">取り消したい電子メールのメッセージ ID を複数の方法で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-128">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="f06f4-129">このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-129">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="f06f4-130">セキュリティ&amp; /コンプライアンスセンターのメッセージ追跡を使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="f06f4-130">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="f06f4-131">[セキュリティ & コンプライアンスセンターで、新しいメッセージの追跡](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者によって電子メールを検索します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-131">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="f06f4-132">電子メールを見つけたら、それを選択して**メッセージ追跡の詳細**ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-132">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="f06f4-133">**詳細情報**を展開して、メッセージ ID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-133">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="f06f4-134">セキュリティ&amp; /コンプライアンスセンターで Office メッセージの暗号化レポートを使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="f06f4-134">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="f06f4-135">セキュリティ&amp; /コンプライアンスセンターで、[メッセージの**暗号化] レポート**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-135">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="f06f4-136">このレポートの詳細については、「[セキュリティ&amp;センターのコンプライアンスセンターで電子メールのセキュリティレポートを表示する](../security/office-365-security/view-email-security-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f06f4-136">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="f06f4-137">[**詳細の表示**] テーブルを選択し、取り消すメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-137">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="f06f4-138">メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-138">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="f06f4-139">手順 2. </span><span class="sxs-lookup"><span data-stu-id="f06f4-139">Step 2.</span></span> <span data-ttu-id="f06f4-140">メールが revocable かどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="f06f4-140">Verify that the mail is revocable</span></span>

<span data-ttu-id="f06f4-141">メッセージを取り消すことができるかどうかを確認するには、セキュリティ&amp;コンプライアンスセンターの**詳細**表で、[失効状態] フィールドが [暗号化] レポートに表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-141">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="f06f4-142">Windows PowerShell を使用して特定の電子メールメッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-142">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="f06f4-143">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-143">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f06f4-144">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f06f4-144">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f06f4-145">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-145">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="f06f4-146">このコマンドは、メッセージの件名と、メッセージが revocable であるかどうかを返します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-146">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="f06f4-147">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-147">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="f06f4-148">手順 3. </span><span class="sxs-lookup"><span data-stu-id="f06f4-148">Step 3.</span></span> <span data-ttu-id="f06f4-149">メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="f06f4-149">Revoke the mail</span></span>

<span data-ttu-id="f06f4-150">取り消したい電子メールのメッセージ ID がわかっていて、そのメッセージが revocable であることを確認したら、セキュリティ&amp;コンプライアンスセンターまたは Windows PowerShell を使用して電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="f06f4-150">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="f06f4-151">セキュリティ&amp; /コンプライアンスセンターを使用してメッセージを取り消すには</span><span class="sxs-lookup"><span data-stu-id="f06f4-151">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="f06f4-152">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、セキュリティ & コンプライアンスセンターに接続します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-152">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f06f4-153">[**暗号化レポート**] の [メッセージの**詳細**] テーブルで、[**メッセージの取り消し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-153">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="f06f4-154">Windows PowerShell を使用して電子メールを失効させるには、OMEMessageRevocation コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-154">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="f06f4-155">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://aka.ms/exopowershell)します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-155">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f06f4-156">OMEMessageRevocation コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-156">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="f06f4-157">電子メールが失効したかどうかを確認するには、次のようにして、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-157">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="f06f4-158">失効が成功した場合、コマンドレットは次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f06f4-158">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="f06f4-159">Office 365 の詳細なメッセージの暗号化に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="f06f4-159">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="f06f4-160">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="f06f4-160">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="f06f4-161">Office 365 の高度なメッセージの暗号化-電子メールの有効期限</span><span class="sxs-lookup"><span data-stu-id="f06f4-161">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="f06f4-162">メッセージポリシーとコンプライアンスサービスの説明</span><span class="sxs-lookup"><span data-stu-id="f06f4-162">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
