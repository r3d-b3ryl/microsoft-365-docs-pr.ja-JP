---
title: 送信者ドメインの洞察を修正する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの送信者ドメインの洞察を修正する方法について説明します。
ms.openlocfilehash: c4cf4a87ad770325ca6ad2f0b87ac8ce52c345c2
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818833"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="75e3f-103">送信者ドメインの洞察を修正する</span><span class="sxs-lookup"><span data-stu-id="75e3f-103">Fix sender domain insight</span></span>

<span data-ttu-id="75e3f-104">Microsoft 365 では、内部のオンプレミスの電子メール環境から Microsoft 365 に送信されるメッセージで、特定のセキュリティ条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e3f-104">Microsoft 365 requires messages sending from internal on-premises email environments to Microsoft 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="75e3f-105">送信元の IP アドレスまたは証明書を使用して、オンプレミスの電子メールサーバーからの SMTP 接続を認証するために、Microsoft 365 で受信コネクタを作成しました。</span><span class="sxs-lookup"><span data-stu-id="75e3f-105">You've created an inbound connector in Microsoft 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="75e3f-106">オンプレミスの電子メールサーバーを、Microsoft 365 経由で外部世界に中継するように構成しました。</span><span class="sxs-lookup"><span data-stu-id="75e3f-106">You've configured your on-premises email server to relay email via Microsoft 365 to external world.</span></span>

- <span data-ttu-id="75e3f-107">構成では、次のいずれかのステートメントが true になります。</span><span class="sxs-lookup"><span data-stu-id="75e3f-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="75e3f-108">送信者の電子メールドメインが組織に登録されている。</span><span class="sxs-lookup"><span data-stu-id="75e3f-108">The sender's email domain is registered in your organization.</span></span> <span data-ttu-id="75e3f-109">詳細については、「Office 365 でドメインを追加する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75e3f-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="75e3f-110">オンプレミスの電子メールサーバーが、証明書を使用して Microsoft 365 に電子メールを送信するように構成されています。証明書は、microsoft 365 に登録したドメイン名と完全に一致しており、そのドメインを使用して Microsoft 365 に証明書ベースのコネクタが作成されています。</span><span class="sxs-lookup"><span data-stu-id="75e3f-110">Your on-premises email server is configured to use a certificate to send email to Microsoft 365, the certificate contains or exactly matches a domain name that you've registered in Microsoft 365, and you've created a certificate based connector in Microsoft 365 with that domain.</span></span> 

<span data-ttu-id="75e3f-111">条件を満たしていないメッセージは、組織には含まれず、拒否される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75e3f-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="75e3f-112">「**送信者ドメインを修正**する」には、オンプレミスの環境からの、条件に一致しないメールが表示されます。これにより、オンプレミスの電子メール環境にある潜在的に侵害されたコンピューターやユーザーアカウントを特定し、修復のアクションを実行するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="75e3f-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの送信者ドメインの洞察を修正する](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="75e3f-114">[詳細の**表示**] をクリックすると、次の図に示すように、詳細を含む別のウィジェットに移動します。</span><span class="sxs-lookup"><span data-stu-id="75e3f-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![「送信者ドメインを修正する」の詳細ウィジェット](../../media/sender-domain-view-details.png)

<span data-ttu-id="75e3f-116">Office 365 にメッセージを配信するために使用された受信コネクタが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75e3f-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="75e3f-117">[**サンプルメッセージ id の表示**] をクリックして、オンプレミスの電子メール環境から送信されたメッセージの詳細を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="75e3f-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="75e3f-118">これらのメッセージは Office 365 によって拒否されたため、メッセージ追跡を使用することはできませんが、サンプルのメッセージ id を使用してオンプレミスの電子メール環境内のメッセージを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="75e3f-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![「Fix sender domain insights」のサンプルメッセージ id を表示する](../../media/sender-domain-view-sample-message-ids.png)

## <a name="related-topics"></a><span data-ttu-id="75e3f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="75e3f-120">Related topics</span></span>

<span data-ttu-id="75e3f-121">メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75e3f-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
