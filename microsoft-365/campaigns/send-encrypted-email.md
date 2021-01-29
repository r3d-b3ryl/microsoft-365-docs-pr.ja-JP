---
title: 暗号化された電子メールを送信する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlook を使用して暗号化された電子メールを送信する方法について学習します。
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044218"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="38137-103">機密情報を暗号化またはラベル付けする</span><span class="sxs-lookup"><span data-stu-id="38137-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="38137-104">データとキャンペーン情報は重要であり、多くの場合は機密です。</span><span class="sxs-lookup"><span data-stu-id="38137-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="38137-105">暗号化ラベルと機密ラベルを使用してこの機密情報を保護し、ユーザーと電子メールの受信者が必要な機密で情報を扱うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38137-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="38137-106">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="38137-106">Best practices</span></span>

<span data-ttu-id="38137-107">機密情報または機密情報を含むメールを送信する前に、次の機能をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="38137-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="38137-108">**暗号化:** 電子メールを暗号化して、メール内の情報のプライバシーを保護できます。</span><span class="sxs-lookup"><span data-stu-id="38137-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="38137-109">電子メール メッセージを暗号化すると、読み取り可能なプレーン テキストからスcrambled cypher テキストに変換されます。</span><span class="sxs-lookup"><span data-stu-id="38137-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="38137-110">メッセージの暗号化に使用された公開キーと一致する公開キーを持つ受信者だけが、メッセージを読み取りのために解読できます。</span><span class="sxs-lookup"><span data-stu-id="38137-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="38137-111">ただし、対応するプライベート キーを持つ受信者には、暗号化できないテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38137-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="38137-112">管理者は、特定の条件を満たすメッセージを自動的に暗号化するルールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="38137-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="38137-113">たとえば、管理者は、組織外に送信されたメッセージすべて、または特定の単語または語句をメンションしているすべてのメッセージを暗号化するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="38137-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="38137-114">暗号化ルールは自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="38137-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="38137-115">**[Sensitivity labels] (感度ラベル):** キャンペーンでは、ファイルやメールに適用できるラベルを設定して、キャンペーンの情報保護ポリシーに準拠し続けることもできます。</span><span class="sxs-lookup"><span data-stu-id="38137-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="38137-116">ラベルを設定すると、ラベルは、たとえばメッセージのヘッダーとして表示されるなど、送信された場合でも、電子メールと一緒に保持されます。</span><span class="sxs-lookup"><span data-stu-id="38137-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![ラベルと暗号化の吹き出しを含む電子メールの図](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="38137-118">設定する</span><span class="sxs-lookup"><span data-stu-id="38137-118">Set it up</span></span>

<span data-ttu-id="38137-119">定義済みのルールを満たしないメッセージを暗号化する場合や、管理者がルールを設定しない場合は、メッセージを送信する前にさまざまな暗号化ルールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="38137-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="38137-120">Outlook 2013 または 2016、または Outlook 2016 for Mac から暗号化されたメッセージを送信するには、[オプション **] > [** アクセス許可] を選択し、必要な保護オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="38137-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="38137-121">Outlook on the web で [保護] ボタンを選択して、暗号化されたメッセージを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="38137-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="38137-122">詳細については、Outlook for PC での暗号化されたメッセージの送信、表示、および返信 [に関するページを参照してください](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。</span><span class="sxs-lookup"><span data-stu-id="38137-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="38137-123">管理設定</span><span class="sxs-lookup"><span data-stu-id="38137-123">Admin settings</span></span>

<span data-ttu-id="38137-124">[Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)の電子メール暗号化でのメール暗号化の設定についてすべて学習できます。</span><span class="sxs-lookup"><span data-stu-id="38137-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="38137-125">電子メール メッセージを自動的に暗号化する</span><span class="sxs-lookup"><span data-stu-id="38137-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="38137-126">管理者は、メール フロー ルールを作成して、キャンペーンから送信および受信される電子メール メッセージを自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="38137-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="38137-127">送信電子メール メッセージを暗号化するルールを設定し、組織内から送信される暗号化されたメッセージや、組織から送信された暗号化されたメッセージへの返信から暗号化を削除します。</span><span class="sxs-lookup"><span data-stu-id="38137-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="38137-128">新しい OME (Office Message Encryption) 機能を使用して電子メール メッセージを暗号化するメール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="38137-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="38137-129">Exchange 管理センター (EAC) を使用して、新しい OME 機能を使用してメッセージの暗号化をトリガーするメール フロー ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="38137-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="38137-130">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている、仕事用または学校用のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="38137-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="38137-131">[管理者] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="38137-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="38137-132">In the admin center, choose **Admin centers > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="38137-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="38137-133">詳細については、「電子メール メッセージを [暗号化するメール フロー ルールの定義」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。</span><span class="sxs-lookup"><span data-stu-id="38137-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="38137-134">暗号化メッセージをブランド化する</span><span class="sxs-lookup"><span data-stu-id="38137-134">Brand your encryption messages</span></span>

<span data-ttu-id="38137-135">キャンペーン のブランド化を適用して、メール メッセージの外観とテキストをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="38137-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="38137-136">詳細については、「暗号化された [メッセージに組織のブランドを追加する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)。</span><span class="sxs-lookup"><span data-stu-id="38137-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>
