---
title: Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: カスタム Office 365 Advanced Message Encryptionを使用してメールの有効期限を設定することで、電子メールのセキュリティを拡張するために使用します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927787"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="9ebb7-103">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する</span><span class="sxs-lookup"><span data-stu-id="9ebb7-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="9ebb7-104">Office 365 Advanced Message Encryptionは[、Microsoft 365 Enterprise E5、Office 365](https://www.microsoft.com/microsoft-365/enterprise/home)E5、Microsoft 365 E5 (非営利スタッフ価格)、Office 365 Enterprise E5 (非営利スタッフ価格)、および Office 365 Education A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="9ebb7-105">組織に Office 365 Advanced Message Encryption を含めないサブスクリプションがある場合は、Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格) の Microsoft 365 E5 Compliance SKU アドオン、または Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Office 365 SKU の Office 365 Advanced Compliance SKU アドオンを使用して購入できます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="9ebb7-106">ユーザーが OME ポータルを使用して暗号化されたメールにアクセスする外部受信者に送信するメールに対して、メッセージの有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="9ebb7-107">Windows PowerShell で有効期限を指定するカスタム ブランド テンプレートを使用して、受信者に OME ポータルを使用して組織から送信された暗号化されたメールを表示して返信を強制します。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="9ebb7-108">グローバル管理者Office 365、会社のブランドを適用して組織の電子メール メッセージの外観をカスタマイズするときに、これらの電子メール メッセージの有効期限を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="9ebb7-109">このOffice 365 Advanced Message Encryption、組織から送信される暗号化された電子メール用に複数のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="9ebb7-110">テンプレートを使用すると、受信者がユーザーから送信されたメールにアクセスできる期間を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="9ebb7-111">有効期限が設定されたメールをエンド ユーザーが受信すると、ラッパー メールに有効期限が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="9ebb7-112">ユーザーが期限切れのメールを開こうとすると、OME ポータルにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="9ebb7-113">メールの有効期限は、外部受信者にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="9ebb7-114">カスタム Office 365 Advanced Message Encryptionを適用すると、Office 365 はテンプレートを適用するメール フロー ルールに適合するメールにラッパーを適用します。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="9ebb7-115">さらに、カスタム ブランドを使用する場合にのみ有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="9ebb7-116">PowerShell を使用してメールの有効期限を強制するカスタム ブランド テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="9ebb7-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="9ebb7-117">[ConnectグローバルExchange Onlineアクセス](/powershell/exchange/connect-to-exchange-online-powershell)許可を持つアカウントを使用して PowerShell を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="9ebb7-118">このコマンドレットをNew-OMEConfigurationします。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="9ebb7-119">ここで、</span><span class="sxs-lookup"><span data-stu-id="9ebb7-119">Where:</span></span>

- <span data-ttu-id="9ebb7-120">`Identity` は、カスタム テンプレートの名前です。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="9ebb7-121">`ExternalMailExpiryInDays` 受信者が期限切れになる前にメールを保持できる日数を識別します。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="9ebb7-122">1 ~ 730 日間の任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ebb7-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="9ebb7-123">詳細については、Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="9ebb7-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="9ebb7-124">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="9ebb7-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="9ebb7-125">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする</span><span class="sxs-lookup"><span data-stu-id="9ebb7-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="9ebb7-126">メッセージ ポリシーとコンプライアンス サービスの説明</span><span class="sxs-lookup"><span data-stu-id="9ebb7-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)