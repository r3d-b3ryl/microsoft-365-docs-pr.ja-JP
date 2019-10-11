---
title: Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 管理者は、Office 365 Advanced Message Encryption で暗号化された特定の電子メールを取り消すことができます。
ms.openlocfilehash: 7adc5713c8753e0caf780bbacf98519665458c52
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435551"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="6b721-103">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする</span><span class="sxs-lookup"><span data-stu-id="6b721-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="6b721-104">電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="6b721-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="6b721-105">Office 365 の高度なメッセージの暗号化は、 [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体の価格)、Office 365 Enterprise E5 (非営利スタッフの価格)、office の365教育用 A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b721-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="6b721-106">Office 365 Advanced Message Encryption を含まないサブスクリプションが組織にある場合は、microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ料金)、または Office 365 Advanced を使用365して購入できます。コンプライアンス SKU アドオン Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフの価格)、または Office 365 Sku。</span><span class="sxs-lookup"><span data-stu-id="6b721-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="6b721-107">この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。</span><span class="sxs-lookup"><span data-stu-id="6b721-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="6b721-108">Office 365 Advanced Message Encryption を使用してメッセージを暗号化し、Office 365 管理者の場合は、特定の条件下でメッセージを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6b721-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="6b721-109">この記事では、失効が可能な状況とその方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b721-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="6b721-110">取り消すことができる暗号化された電子メール</span><span class="sxs-lookup"><span data-stu-id="6b721-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="6b721-111">受信者がリンクベースの、ブランド化された電子メールを受信した場合は、暗号化された電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6b721-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="6b721-112">受信者が、サポートされている Outlook クライアントでネイティブインライン環境を受信した場合は、それらの電子メールを取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6b721-112">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="6b721-113">受信者がリンクベースの機能を受信するか、またはインラインでの使用を許可するかは、受信者の id の種類によって異なります。 Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com users) は、サポートされている Outlook クライアントでインラインの動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b721-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="6b721-114">Gmail 受信者など、他のすべての受信者の種類は、リンクベースの処理を行います。</span><span class="sxs-lookup"><span data-stu-id="6b721-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="6b721-115">取り消された暗号化された電子メールの受信者向けの手順</span><span class="sxs-lookup"><span data-stu-id="6b721-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="6b721-116">電子メールが失効されると、受信者は Office 365 メッセージ暗号化ポータルを経由して暗号化された電子メールにアクセスしたときにエラーを受信します。 "メッセージは送信者によって取り消されました"。</span><span class="sxs-lookup"><span data-stu-id="6b721-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![取り消された暗号化された電子メールを示すスクリーンショット。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="6b721-118">暗号化された電子メールを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="6b721-118">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="6b721-119">手順 1.</span><span class="sxs-lookup"><span data-stu-id="6b721-119">Step 1.</span></span> <span data-ttu-id="6b721-120">電子メールのメッセージ ID を取得する</span><span class="sxs-lookup"><span data-stu-id="6b721-120">Obtain the Message ID of the email</span></span>

<span data-ttu-id="6b721-121">暗号化されたメールを取り消すには、メールのメッセージ ID を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b721-121">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="6b721-122">MessageId は通常、次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="6b721-122">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="6b721-123">取り消したい電子メールのメッセージ ID を複数の方法で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6b721-123">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="6b721-124">このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b721-124">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="6b721-125">セキュリティ&amp; /コンプライアンスセンターのメッセージ追跡を使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="6b721-125">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="6b721-126">[Office 365 セキュリティ & コンプライアンスセンターで、新しいメッセージの追跡](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者別に電子メールを検索します。</span><span class="sxs-lookup"><span data-stu-id="6b721-126">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="6b721-127">電子メールを見つけたら、それを選択して**メッセージ追跡の詳細**ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6b721-127">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="6b721-128">**詳細情報**を展開して、メッセージ ID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="6b721-128">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="6b721-129">セキュリティ&amp; /コンプライアンスセンターで Office メッセージの暗号化レポートを使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="6b721-129">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="6b721-130">セキュリティ&amp; /コンプライアンスセンターで、[メッセージの**暗号化] レポート**に移動します。</span><span class="sxs-lookup"><span data-stu-id="6b721-130">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="6b721-131">このレポートの詳細については、「[セキュリティ&amp;センターのコンプライアンスセンターで電子メールのセキュリティレポートを表示する](view-email-security-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b721-131">For information on this report, see [View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md).</span></span>

2. <span data-ttu-id="6b721-132">[**詳細の表示**] テーブルを選択し、取り消すメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="6b721-132">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="6b721-133">メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b721-133">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="6b721-134">手順 2.</span><span class="sxs-lookup"><span data-stu-id="6b721-134">Step 2.</span></span> <span data-ttu-id="6b721-135">メールが revocable かどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="6b721-135">Verify that the mail is revocable</span></span>

<span data-ttu-id="6b721-136">メッセージを取り消すことができるかどうかを確認するには、セキュリティ&amp;コンプライアンスセンターの**詳細**表で、[失効状態] フィールドが [暗号化] レポートに表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b721-136">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="6b721-137">Windows Powershell を使用して特定の電子メールメッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b721-137">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="6b721-138">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="6b721-138">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="6b721-139">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b721-139">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="6b721-140">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b721-140">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="6b721-141">これにより、メッセージの件名と、メッセージが revocable かどうかが返されます。</span><span class="sxs-lookup"><span data-stu-id="6b721-141">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="6b721-142">For example,</span><span class="sxs-lookup"><span data-stu-id="6b721-142">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="6b721-143">手順 3.</span><span class="sxs-lookup"><span data-stu-id="6b721-143">Step 3.</span></span> <span data-ttu-id="6b721-144">メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="6b721-144">Revoke the mail</span></span>

<span data-ttu-id="6b721-145">取り消したい電子メールのメッセージ ID がわかっていて、そのメッセージが revocable であることを確認したら、セキュリティ&amp;コンプライアンスセンターまたは Windows Powershell を使用して電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6b721-145">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="6b721-146">セキュリティ&amp; /コンプライアンスセンターを使用してメッセージを取り消すには</span><span class="sxs-lookup"><span data-stu-id="6b721-146">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="6b721-147">セキュリティ&amp; /コンプライアンスセンターで電子メールを取り消すには、暗号化レポートの [メッセージの**詳細**] テーブルで、[**メッセージの取り消し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b721-147">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="6b721-148">OMEMessageRevocation コマンドレットを使用して、Windows Powershell を使用して電子メールを失効させることができます。</span><span class="sxs-lookup"><span data-stu-id="6b721-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="6b721-149">[Exchange Online PowerShell への接続](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="6b721-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="6b721-150">OMEMessageRevocation コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="6b721-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="6b721-151">電子メールが失効したかどうかを確認するには、次のようにして、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b721-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="6b721-152">失効が成功した場合、コマンドレットは次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="6b721-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="6b721-153">Office 365 の詳細なメッセージの暗号化に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="6b721-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="6b721-154">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="6b721-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="6b721-155">Office 365 の高度なメッセージの暗号化-電子メールの有効期限</span><span class="sxs-lookup"><span data-stu-id="6b721-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="6b721-156">メッセージポリシーとコンプライアンスサービスの説明</span><span class="sxs-lookup"><span data-stu-id="6b721-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
