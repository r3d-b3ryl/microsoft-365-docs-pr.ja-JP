---
title: Office 365 Advanced Message Encryption
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
description: Office 365 の高度なメッセージ暗号化では、管理者が Office 365 web ポータルを使用して暗号化された電子メールにアクセスを期限切れにし、取り消すことができるようになります。
ms.openlocfilehash: eb6e95b1cbf24ab19df6a595c34721c84c831211
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435511"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="49967-103">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="49967-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="49967-104">Office 365 の高度なメッセージの暗号化は、 [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体の価格)、Office 365 Enterprise E5 (非営利スタッフの価格)、office の365教育用 A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="49967-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="49967-105">Office 365 Advanced Message Encryption を含まないサブスクリプションが組織にある場合は、microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ料金)、または Office 365 Advanced を使用365して購入できます。コンプライアンス SKU アドオン Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフの価格)、または Office 365 Sku。</span><span class="sxs-lookup"><span data-stu-id="49967-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="49967-106">Office 365 の高度なメッセージ暗号化を使用すると、お客様は、外部の受信者により柔軟な制御と暗号化された電子メールへのアクセスを必要とするコンプライアンス義務を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="49967-106">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="49967-107">Office 365 の高度なメッセージ暗号化を使用すると、自動ポリシーにより、組織の外部で共有される機密メールを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="49967-107">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="49967-108">これらのポリシーは、PII、財務、健康 Id などの機密情報の種類を識別するために構成したり、保護を強化するためにキーワードを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="49967-108">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="49967-109">ポリシーを構成したら、ポリシーをカスタムのブランド化された電子メールテンプレートとペアにして、ポリシーに適合する電子メールの追加の制御の有効期限を追加します。</span><span class="sxs-lookup"><span data-stu-id="49967-109">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="49967-110">また、管理者は、メールへのアクセスをいつでも取り消すことにより、セキュリティで保護された web ポータルを介して外部からアクセスされる暗号化メールを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="49967-110">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="49967-111">外部の受信者に送信される電子メールの有効期限は、失効日と設定のみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="49967-111">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

<span data-ttu-id="49967-112">Office 365 の高度なメッセージ暗号化では、カスタムブランド設定テンプレートを適用するたびに、Office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。</span><span class="sxs-lookup"><span data-stu-id="49967-112">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Office 365 applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="49967-113">メッセージを失効させることができます。また、ユーザーがポータル経由で受信するメッセージに有効期限日を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="49967-113">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="49967-114">つまり、カスタムブランド化テンプレートが適用されている電子メール。</span><span class="sxs-lookup"><span data-stu-id="49967-114">In other words, email that has a custom branding template applied.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="49967-115">Office 365 Advanced Message Encryption の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="49967-115">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="49967-116">次のトピックでは、高度なメッセージ暗号化の設定方法と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49967-116">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="49967-117">組織には、Office 365 Advanced Message Encryption を含むサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="49967-117">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="49967-118">サポートされているサブスクリプションの詳細については、「[メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49967-118">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="49967-119">Office 365 メッセージの暗号化が既にセットアップされていない場合は、「 [365 office の新しいメッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49967-119">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="49967-120">[Office 365 Advanced Message Encryption で暗号化された電子メールの有効期限日を設定](ome-advanced-expiration.md)します。</span><span class="sxs-lookup"><span data-stu-id="49967-120">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="49967-121">セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを期限切れにすることによって保護を強化する自動ポリシーを使用して、組織外で共有する機密メールを制御</span><span class="sxs-lookup"><span data-stu-id="49967-121">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="49967-122">[Office 365 の高度なメッセージ暗号化によって暗号化された電子メールを取り消し](revoke-ome-encrypted-mail.md)ます。</span><span class="sxs-lookup"><span data-stu-id="49967-122">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="49967-123">セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを取り消すことにより、組織の外部で共有される機密メールを制御し、保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="49967-123">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  
