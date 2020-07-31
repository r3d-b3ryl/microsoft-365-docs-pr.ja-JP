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
description: Outlook を使用して暗号化された電子メールを送信する方法について説明します。
ms.openlocfilehash: f5184de55ce07d5e669e98afb6e627833071c4ba
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526878"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="79bf6-103">機密情報を暗号化またはラベル付けする</span><span class="sxs-lookup"><span data-stu-id="79bf6-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="79bf6-104">データおよびキャンペーン情報は重要であり、機密であることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="79bf6-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="79bf6-105">暗号化と機密情報のラベルを使用してこの機密情報を保護すると、電子メールの受信者は、必要な機密度で情報を扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="79bf6-106">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="79bf6-106">Best practices</span></span>

<span data-ttu-id="79bf6-107">機密情報または機密情報を含む電子メールを送信する前に、次のことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="79bf6-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="79bf6-108">**暗号化:** 電子メールを暗号化して、電子メール内の情報のプライバシーを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="79bf6-109">電子メールメッセージを暗号化すると、読み取り可能なプレーンテキストからスクランブル cypher テキストに変換されます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="79bf6-110">メッセージの暗号化に使用された公開キーと一致する秘密キーを持つ受信者のみが、メッセージの読み取りのための解読を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="79bf6-111">ただし、対応する秘密キーを持たない受信者は、認識できないテキストを認識します。</span><span class="sxs-lookup"><span data-stu-id="79bf6-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="79bf6-112">管理者は、特定の条件を満たすメッセージを自動的に暗号化するルールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="79bf6-113">たとえば、組織外から送信されたすべてのメッセージ、または特定の単語や語句を含むすべてのメッセージを暗号化するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="79bf6-114">暗号化ルールは自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="79bf6-115">**機密ラベル:** キャンペーンでは、ファイルや電子メールに適用して、キャンペーンの情報保護ポリシーに準拠させることができる、機密ラベルを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="79bf6-116">ラベルを設定すると、ラベルが送信された場合でも、メッセージのヘッダーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![ラベルと暗号化の吹き出しが付いた電子メールの図](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="79bf6-118">設定する</span><span class="sxs-lookup"><span data-stu-id="79bf6-118">Set it up</span></span>

<span data-ttu-id="79bf6-119">事前に定義されたルールに準拠していないメッセージを暗号化する場合、または管理者がルールを設定していない場合は、メッセージを送信する前にさまざまな暗号化ルールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="79bf6-120">暗号化されたメッセージを Outlook 2013 または2016、または Outlook 2016 for Mac から送信するには、[**オプション > のアクセス許可**] を選択し、必要な保護オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="79bf6-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="79bf6-121">また、暗号化されたメッセージを送信するには、Outlook on the web で [**保護**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79bf6-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="79bf6-122">詳細については、「 [Outlook FOR PC での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79bf6-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="79bf6-123">管理設定</span><span class="sxs-lookup"><span data-stu-id="79bf6-123">Admin settings</span></span>

<span data-ttu-id="79bf6-124">電子メールの暗号化の設定については、「 [Microsoft 365 の電子メールの暗号化」](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79bf6-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="79bf6-125">電子メールメッセージを自動的に暗号化する</span><span class="sxs-lookup"><span data-stu-id="79bf6-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="79bf6-126">管理者は、メールフロールールを作成して、キャンペーンから送受信される電子メールメッセージを自動的に保護することができます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="79bf6-127">送信電子メールメッセージを暗号化するルールを設定し、組織内から送信される暗号化されたメッセージ、または組織から送信された暗号化メッセージへの返信から暗号化を削除します。</span><span class="sxs-lookup"><span data-stu-id="79bf6-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="79bf6-128">メールフロールールを作成して、新しい Office 365 Message Encryption (OME) 機能を使用して電子メールメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="79bf6-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="79bf6-129">Exchange 管理センター (EAC) を使用して、新しい OME 機能でメッセージの暗号化をトリガーするためのメールフロールールを定義します。</span><span class="sxs-lookup"><span data-stu-id="79bf6-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="79bf6-130">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用している場合は、サインインします。</span><span class="sxs-lookup"><span data-stu-id="79bf6-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span> 
2. <span data-ttu-id="79bf6-131">[管理] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="79bf6-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="79bf6-132">管理センターで、[ **Exchange > 管理センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79bf6-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="79bf6-133">詳細については、「メール[フロールールを定義して電子メールメッセージを暗号化する](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79bf6-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="79bf6-134">暗号化メッセージをブランド化する</span><span class="sxs-lookup"><span data-stu-id="79bf6-134">Brand your encryption messages</span></span>

<span data-ttu-id="79bf6-135">また、キャンペーンブランドを適用して、電子メールメッセージの外観やテキストをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="79bf6-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="79bf6-136">詳細については、「[組織のブランドを暗号化されたメッセージに追加する](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79bf6-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

