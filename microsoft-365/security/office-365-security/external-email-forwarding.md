---
title: 外部メール転送の構成と制御、自動転送、5.7.520 アクセス拒否、外部転送の無効化、管理者が外部転送を無効にした、送信スパム対策ポリシー
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 7cb2ab9c6987900f2b53a17c3eda49001bca4d84
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898054"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="f5d4a-103">Office 365 で外部電子メール転送を構成する</span><span class="sxs-lookup"><span data-stu-id="f5d4a-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="f5d4a-104">外部転送は、発信の *スパム対策ポリシー* によって制御され、構成された設定に基づいてユーザーのスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="f5d4a-105">現在、3つの設定がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="f5d4a-106">**Automatic** -このモードでは、転送されたメッセージが許可されているかどうかをシステムが判断します。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="f5d4a-107">これは既定のモードで、このモードでは、システムによって自動的に外部転送がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="f5d4a-108">**オン** -自動外部転送が許可されていて、制限されていません。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="f5d4a-109">**Off** -自動外部転送が無効になり、エンドユーザーに配信不能レポート (NDR) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="f5d4a-110">これらの設定を構成する方法の詳細については、「 [EOP で送信スパムフィルターを構成](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="f5d4a-111">外部メール転送を制御する</span><span class="sxs-lookup"><span data-stu-id="f5d4a-111">Controlling external email forwarding</span></span>

<span data-ttu-id="f5d4a-112">組織の管理者として、組織外の受信トレイルールまたは SMTP 転送を使用して電子メールを自動的に転送できるユーザーを制限または制御するには、会社の要件があります。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="f5d4a-113">メールの転送は便利な機能ですが、組織またはパートナーを攻撃するために利用できる攻撃者に情報を提供することによっても、情報の漏洩によってリスクが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="f5d4a-114">Office 365 では、受信トレイルールまたはメールボックス構成のいずれかを使用した自動の外部転送を許可しません。これは、セキュリティで保護された既定のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="f5d4a-115">ただし、管理者は組織内のすべてのユーザーまたは一部のユーザーについてこれらの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="f5d4a-116">内部ユーザー間でのメッセージ転送は、このような変更による影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="f5d4a-117">Office 365 で外部アドレスへの自動転送を無効にすると、 [メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) の投稿によって伝達された詳細をフェーズ内でロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="f5d4a-118">管理者がこれらの変更を準備するには、事前にポリシーを変更して、ユーザーに混乱が発生しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="f5d4a-119">組織内の自動転送 (受信トレイルールまたは SMTP 転送) を使用しているユーザーの詳細については、「 [自動転送](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide)されたメッセージ」レポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="f5d4a-120">このポリシーが他の自動転送コントロールとどのように連動するか</span><span class="sxs-lookup"><span data-stu-id="f5d4a-120">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="f5d4a-121">管理者として、 [リモートドメイン](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) での自動転送をブロックしたり、Exchange トランスポートルール (etr) を使用したりするなど、他の種類のコントロールが既に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-121">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="f5d4a-122">これらのコントロールは、この特定の機能に依存しません。たとえば、リモートドメインへの自動転送を許可し、送信スパムポリシーによる自動転送をブロックすると、自動的に転送されるメッセージがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-122">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="f5d4a-123">同様に、送信スパムポリシーで自動転送を許可していて、それを ETR またはリモートドメインでブロックする場合、メッセージはこれらのコントロールのいずれかによってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-123">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="f5d4a-124">これにより、たとえば、送信スパムポリシーで自動転送を許可したり、リモートドメインを利用して、ユーザーがメッセージを自動的に転送できるドメインを制御したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-124">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="f5d4a-125">ブロックされたメール転送メッセージ</span><span class="sxs-lookup"><span data-stu-id="f5d4a-125">The blocked email forwarding message</span></span>

<span data-ttu-id="f5d4a-126">メッセージが自動的に転送されると検出され、組織 *のポリシーに* よって **配信不能レポート (NDR)** がエンドユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-126">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="f5d4a-127">レポートには、メッセージが配信されなかったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-127">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="f5d4a-128">NDR の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f5d4a-128">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
