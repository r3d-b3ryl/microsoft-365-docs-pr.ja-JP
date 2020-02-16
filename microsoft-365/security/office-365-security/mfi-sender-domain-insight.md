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
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの送信者ドメインの洞察を修正する方法について説明します。
ms.openlocfilehash: 2db1b971ef39f8b207b349ca53237ff87cc9193e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082574"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="3b9b1-103">送信者ドメインの洞察を修正する</span><span class="sxs-lookup"><span data-stu-id="3b9b1-103">Fix sender domain insight</span></span>

<span data-ttu-id="3b9b1-104">Office 365 では、内部のオンプレミスの電子メール環境から Office 365 に送信されるメッセージで、特定のセキュリティ条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-104">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="3b9b1-105">送信元の IP アドレスまたは証明書を使用して、オンプレミスの電子メールサーバーからの SMTP 接続を認証するために、Office 365 で受信コネクタを作成しました。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-105">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="3b9b1-106">Office 365 を介して外部の world に電子メールを中継するようにオンプレミスの電子メールサーバーが構成されている。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-106">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="3b9b1-107">構成では、次のいずれかのステートメントが true になります。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="3b9b1-108">送信者の電子メールドメインは、Office 365 組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-108">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="3b9b1-109">詳細については、「Office のドメインを追加する365」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="3b9b1-110">オンプレミスの電子メールサーバーが、証明書を使用して Office 365 に電子メールを送信するように構成されており、証明書が office 365 に登録したドメイン名と完全に一致していて、それを含む Office 365 に証明書ベースのコネクタが作成されている。領域.</span><span class="sxs-lookup"><span data-stu-id="3b9b1-110">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="3b9b1-111">条件を満たしていないメッセージは、組織には含まれず、拒否される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="3b9b1-112">「**送信者ドメインを修正**する」には、オンプレミスの環境からの、条件に一致しないメールが表示されます。これにより、オンプレミスの電子メール環境にある潜在的に侵害されたコンピューターやユーザーアカウントを特定し、修復のアクションを実行するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの送信者ドメインの洞察を修正する](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="3b9b1-114">[詳細の**表示**] をクリックすると、次の図に示すように、詳細を含む別のウィジェットに移動します。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![「送信者ドメインを修正する」の詳細ウィジェット](../../media/sender-domain-view-details.png)

<span data-ttu-id="3b9b1-116">Office 365 にメッセージを配信するために使用された受信コネクタが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="3b9b1-117">[**サンプルメッセージ id の表示**] をクリックして、オンプレミスの電子メール環境から送信されたメッセージの詳細を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="3b9b1-118">これらのメッセージは Office 365 によって拒否されたため、メッセージ追跡を使用することはできませんが、サンプルのメッセージ id を使用してオンプレミスの電子メール環境内のメッセージを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![「Fix sender domain insights」のサンプルメッセージ id を表示する](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="3b9b1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b9b1-120">See also</span></span>

<span data-ttu-id="3b9b1-121">メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b9b1-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
