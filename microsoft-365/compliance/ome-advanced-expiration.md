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
description: Office 365 の高度なメッセージ暗号化機能が Office 365 メッセージ暗号化 (OME) の上にあるため、電子メールのセキュリティを拡張するには、カスタムブランド化されたテンプレートを使用して、メールの有効期限を設定します。
ms.openlocfilehash: 90f406ec72eeab0618184336b8b28de452a5e3c6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597824"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="3d68c-103">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する</span><span class="sxs-lookup"><span data-stu-id="3d68c-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="3d68c-104">Office 365 の高度なメッセージの暗号化は、 [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体の価格)、Office 365 Enterprise E5 (非営利スタッフの価格)、office の365教育用 A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d68c-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="3d68c-105">Office 365 Advanced Message Encryption を含まないサブスクリプションが組織にある場合は、microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ料金)、または Office 365 Advanced を使用365して購入できます。コンプライアンス SKU アドオン Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフの価格)、または Office 365 Sku。</span><span class="sxs-lookup"><span data-stu-id="3d68c-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="3d68c-106">OME ポータルを使用して暗号化された電子メールにアクセスする外部の受信者に送信するユーザーが電子メールでメッセージの有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="3d68c-107">受信者が OME ポータルを使用して、組織によって送信される暗号化された電子メールを、Windows Powershell で有効期限を指定するカスタムブランド化テンプレートを使用して表示および返信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3d68c-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="3d68c-108">O365 グローバル管理者は、会社のブランドを適用して Office 365 組織の電子メールメッセージの外観をカスタマイズする場合、これらの電子メールメッセージの有効期限を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-108">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="3d68c-109">Office 365 Advanced Message Encryption を使用すると、組織から発信される暗号化された電子メール用に複数のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="3d68c-110">テンプレートを使用すると、受信者がユーザーによって送信されたメールにアクセスできる期間を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="3d68c-111">エンドユーザーが有効期限が設定されたメールを受信すると、ユーザーにはラッパーの電子メールの有効期限が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="3d68c-112">ユーザーが期限切れメールを開こうとすると、OME ポータルにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="3d68c-113">電子メールの有効期限は、外部の受信者にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="3d68c-114">Office 365 Advanced Message Encryption では、カスタムブランドを適用するたびに、Office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。</span><span class="sxs-lookup"><span data-stu-id="3d68c-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="3d68c-115">また、カスタムブランド化を使用する場合にのみ、有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="3d68c-116">PowerShell を使用してメールの有効期限を強制するカスタムブランド化テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="3d68c-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="3d68c-117">Office 365 組織のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="3d68c-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="3d68c-118">OMEConfiguration 新しいコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d68c-118">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="3d68c-119">ここで、</span><span class="sxs-lookup"><span data-stu-id="3d68c-119">Where:</span></span>

- <span data-ttu-id="3d68c-120">`Identity`は、カスタムテンプレートの名前です。</span><span class="sxs-lookup"><span data-stu-id="3d68c-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="3d68c-121">`ExternalMailExpiryInDays`受信者が期限切れになる前にメールを保持できる日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d68c-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="3d68c-122">1から730日までの任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d68c-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="3d68c-123">Office 365 の詳細なメッセージの暗号化に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="3d68c-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="3d68c-124">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="3d68c-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="3d68c-125">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする</span><span class="sxs-lookup"><span data-stu-id="3d68c-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="3d68c-126">メッセージポリシーとコンプライアンスサービスの説明</span><span class="sxs-lookup"><span data-stu-id="3d68c-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
