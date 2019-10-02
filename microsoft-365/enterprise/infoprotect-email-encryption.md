---
title: '手順 6: 電子メールの暗号化を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365 の特権アクセス管理について理解して構成します。
ms.openlocfilehash: ef9da1d6aea20ef965b56006d91c4da3c0ad18ab
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370434"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="c7f30-103">手順 6: 電子メールの暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="c7f30-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="c7f30-104">*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="c7f30-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c7f30-106">Microsoft 365 には、3種類の電子メール暗号化があります。</span><span class="sxs-lookup"><span data-stu-id="c7f30-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="c7f30-107">Office のメッセージ暗号化 (OME)</span><span class="sxs-lookup"><span data-stu-id="c7f30-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="c7f30-108">組織外で送信された Exchange Online 電子メールの暗号化。</span><span class="sxs-lookup"><span data-stu-id="c7f30-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="c7f30-109">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="c7f30-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="c7f30-110">電子メールと共に移動する暗号化とアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="c7f30-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="c7f30-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="c7f30-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="c7f30-112">暗号化とデジタル署名による電子メール保護。</span><span class="sxs-lookup"><span data-stu-id="c7f30-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="c7f30-113">はい</span><span class="sxs-lookup"><span data-stu-id="c7f30-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="c7f30-114">OME を使用すると、組織は組織内外のユーザー間で暗号化された電子メールメッセージの送受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="c7f30-115">OME は、Outlook.com、Yahoo!、Gmail、その他の電子メールサービスと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="c7f30-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="c7f30-116">電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c7f30-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![電子メールメッセージの OME 暗号化](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="c7f30-118">暗号化の条件を定義するトランスポートルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="c7f30-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="c7f30-119">ユーザーがルールに一致するメッセージを送信する場合、自動的に暗号化が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="c7f30-120">暗号化されたメッセージを表示するには、受信者はワンタイムパスコードを取得するか、Microsoft アカウントでサインインするか、Microsoft 365 に関連付けられた職場または学校のアカウントでサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="c7f30-121">受信者は、暗号化された返信を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="c7f30-122">暗号化されたメッセージを表示したり、暗号化された返信を送信したりするために、独自の Microsoft 365 サブスクリプションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c7f30-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="c7f30-123">詳細については、「 [Office 365 での暗号化](https://docs.microsoft.com/Office365/SecurityCompliance/ome)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f30-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="c7f30-124">IRM</span><span class="sxs-lookup"><span data-stu-id="c7f30-124">IRM</span></span>

<span data-ttu-id="c7f30-125">Microsoft 365 の IRM は、追加の暗号化を使用して情報を保護し、ユーザーが実行できる操作を指定するインテリジェントポリシーを適用することにより、情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="c7f30-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="c7f30-126">電子メールメッセージの場合は、暗号化に IRM を使用し、使用制限を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="c7f30-127">たとえば、一部の受信者がすべての電子メールを管理する機能を持ち、一部の受信者が電子メールを印刷または転送できないように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="c7f30-128">IRM ポリシーは、Microsoft 365 内で構成されており、SharePoint Online および電子メールメッセージ内のドキュメントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="c7f30-129">IRM で保護された電子メールには、適用されたポリシー設定が含まれており、それと一緒に移動します。</span><span class="sxs-lookup"><span data-stu-id="c7f30-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![電子メールメッセージの IRM 保護](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="c7f30-131">受信者が含まれているポリシーを使用して電子メールを開くと、ポリシー設定を使用して、メッセージを復号化し、受信者が実行できる処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="c7f30-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="c7f30-132">詳細については、「 [Exchange Online での Information Rights Management]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f30-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="c7f30-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="c7f30-133">S/MIME</span></span>

<span data-ttu-id="c7f30-134">S/MIME は、デジタル証明書ベースの電子メールベースの保護ソリューションで、メッセージの暗号化とデジタル署名の両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="c7f30-135">メッセージの暗号化により、指定された受信者だけがメッセージを開き読むことができます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="c7f30-136">デジタル署名は、受信者が送信者の身元を確認し、送信者のみが送信したことを確認するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="c7f30-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![電子メールメッセージの S/MIME 保護](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="c7f30-138">S/MIME は、Microsoft 365 サブスクリプションの他のメールボックスまたは外部ユーザーに電子メールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="c7f30-139">メッセージ暗号化とデジタル署名の両方は、メッセージの暗号化または復号化、およびデジタル署名の作成と検証のための公開キーと秘密キーを含むデジタル証明書を使用することによって可能になります。</span><span class="sxs-lookup"><span data-stu-id="c7f30-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="c7f30-140">S/MIME を使用するには、各受信者の公開キーを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7f30-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="c7f30-141">受信者は、自分の秘密キーを保持します。これは安全なままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7f30-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="c7f30-142">秘密キーが侵害された場合は、新しいデジタル証明書を取得して、公開キーをすべての潜在的な送信者に再配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7f30-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="c7f30-143">詳細については、「[S/MIME によるメッセージの署名と暗号化](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f30-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="c7f30-144">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step6)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c7f30-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c7f30-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="c7f30-145">Next step</span></span>

|||
|:-------|:-----|
|![手順7](./media/stepnumbers/Step7.png)|[<span data-ttu-id="c7f30-147">Office 365 の特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="c7f30-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
