---
title: スパム対策保護 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で、スパム対策保護についてよく寄せられる質問と回答を参照できます。
ms.openlocfilehash: 69d9e72e3be53f0ddd5bc5771493564f364bef54
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209645"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="2f95e-103">スパム対策保護に関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="2f95e-103">Anti-spam protection FAQ</span></span>

<span data-ttu-id="2f95e-104">このトピックでは、exchange Online のメールボックスを使用する Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織に対するマルウェア対策保護に関するよく寄せられる質問と回答について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-104">This topic provides frequently asked questions and answers about anti-malware protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="2f95e-105">検疫に関する質問と回答については、「[検疫に関する FAQ](quarantine-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-105">For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>

<span data-ttu-id="2f95e-106">マルウェア対策保護に関する質問と回答については、「[マルウェア対策保護](anti-malware-protection-faq-eop.md)に関する faq」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="2f95e-107">スプーフィング対策保護に関する質問と回答については、「[スプーフィング対策保護](anti-spoofing-protection-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="by-default-what-happens-to-a-spam-detected-message"></a><span data-ttu-id="2f95e-108">既定では、スパム検出メッセージはどのように処理されますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-108">By default, what happens to a spam-detected message?</span></span>

<span data-ttu-id="2f95e-109">**受信メッセージの場合:** スパムの大部分は、送信元の電子メールサーバーの IP アドレスに基づいて、接続フィルターによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-109">**For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the source email server.</span></span> <span data-ttu-id="2f95e-110">スパム対策ポリシー (スパムフィルターポリシーまたはコンテンツフィルターポリシーとも呼ばれます) は、メッセージを検査し、スパム、一括、またはフィッシングとして分類します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-110">Anti-spam policies (also known as spam filter policies or content filter policies) inspect and classify messages as spam, bulk, or phishing.</span></span> <span data-ttu-id="2f95e-111">既定では、スパムまたは一括として分類されるメッセージは、受信者の迷惑メールフォルダーに配信され、フィッシングとして分類されたメッセージは検疫されます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-111">By default, messages that are classified as spam or bulk are delivered to the recipient's Junk Email folder, while messages classified as phishing are quarantined.</span></span> <span data-ttu-id="2f95e-112">既定のスパム対策ポリシー (すべての受信者に適用されます) を変更することも、特定のユーザーグループに対して厳密な設定を使用してカスタムのスパム対策ポリシーを作成することもできます (たとえば、エグゼクティブに送信されるスパムを検疫できます)。</span><span class="sxs-lookup"><span data-stu-id="2f95e-112">You can modify the default anti-spam policy (applies to all recipients), or you can create custom anti-spam policies with stricter settings for specific groups of users (for example, you can quarantine spam that's sent to executives).</span></span> <span data-ttu-id="2f95e-113">詳細については、「[スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」および「[推奨されるスパム対策ポリシー設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-113">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Recommended anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f95e-114">EOP が社内メールボックスを保護するハイブリッド展開では、オンプレミスの Exchange 組織内の2つの Exchange メールフロールール (トランスポートルールとも呼ばれます) を構成して、メッセージに追加される EOP スパムフィルタリングヘッダーを検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-114">In hybrid deployments where EOP protects on-premises mailboxes, you need to configure two Exchange mail flow rules (also known as transport rules) in your on-premises Exchange organization to detect the EOP spam filtering headers that are added to messages.</span></span> <span data-ttu-id="2f95e-115">詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-115">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

 <span data-ttu-id="2f95e-116">**送信メッセージの場合:** メッセージは、[危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)を経由してルーティングされるか、配信不能レポート (NDR またはバウンスメッセージとも呼ばれる) で送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-116">**For outbound messages:** The message is either routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) or is returned to the sender in a non-delivery report (also known as an NDR or bounce message).</span></span> <span data-ttu-id="2f95e-117">送信スパム保護の詳細については、「[送信スパム制御](outbound-spam-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-117">For more information about outbound spam protection, see [Outbound spam controls](outbound-spam-controls.md).</span></span>

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a><span data-ttu-id="2f95e-118">ゼロ日のスパムバリアントとは何ですか。サービスによってどのように処理されますか。</span><span class="sxs-lookup"><span data-stu-id="2f95e-118">What's a zero-day spam variant and how is it handled by the service?</span></span>

<span data-ttu-id="2f95e-119">ゼロ日のスパムの亜種は、まだ取得または分析されていない最初世代のスパムのバリアントです。そのため、スパム対策フィルターは、それを検出するために利用できる情報をまだ持っていません。</span><span class="sxs-lookup"><span data-stu-id="2f95e-119">A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our anti-spam filters don't yet have any information available for detecting it.</span></span> <span data-ttu-id="2f95e-120">スパムの分類の基準を満たしている場合、スパムの1日のサンプルを取得して分析した後、スパムの分類の条件を満たす場合は、スパム対策フィルターを検出し、"0 日" とは見なされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2f95e-120">After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our anti-spam filters are updated to detect it, and it's no longer considered "zero-day."</span></span>

<span data-ttu-id="2f95e-121">**注:** スパムの送信がゼロであるというメッセージが表示される場合は、サービスの品質向上のために、「[レポートメッセージとファイル](report-junk-email-messages-to-microsoft.md)」に記載されているいずれかの方法を使用して、メッセージを microsoft に送信してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-121">**Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a><span data-ttu-id="2f95e-122">スパム対策保護を提供するサービスを構成する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-122">Do I need to configure the service to provide anti-spam protection?</span></span>

<span data-ttu-id="2f95e-123">サービスにサインアップしてドメインを追加すると、スパムフィルターが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-123">After you sign up for the service and add your domain, spam filtering is automatically enabled.</span></span> <span data-ttu-id="2f95e-124">既定では、スパムフィルターは、追加の構成を必要とせずに (ハイブリッド環境におけるスタンドアロン EOP スタンドアロンのお客様に対して) 保護するように調整されています。</span><span class="sxs-lookup"><span data-stu-id="2f95e-124">By default, spam filtering is tuned to protect you without needing any additional configuration (aside from the previously noted exception for standalone EOP standalone customers in hybrid environments).</span></span> <span data-ttu-id="2f95e-125">管理者は、組織のニーズに合わせて、既定のスパムフィルター設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-125">As an admin, you can edit the default spam filtering settings to best meet the needs of your organization.</span></span> <span data-ttu-id="2f95e-126">さらにきめ細かく設定すると、組織内の特定のユーザー、グループ、またはドメインに適用されるスパム対策ポリシーと送信スパム対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-126">For greater granularity, you can also create anti-spam policies and outbound anti-spam policies that are applied to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="2f95e-127">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-127">Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>

<span data-ttu-id="2f95e-128">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-128">For more information, see the following topics:</span></span>

[<span data-ttu-id="2f95e-129">EOP および Office 365 の ATP セキュリティに関する推奨設定</span><span class="sxs-lookup"><span data-stu-id="2f95e-129">Recommended settings for EOP and Office 365 ATP security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

[<span data-ttu-id="2f95e-130">EOP で接続フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="2f95e-130">Configure connection filtering in EOP</span></span>](configure-the-connection-filter-policy.md)

[<span data-ttu-id="2f95e-131">EOP でスパム対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="2f95e-131">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="2f95e-132">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="2f95e-132">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a><span data-ttu-id="2f95e-133">スパム対策ポリシーを変更した場合、変更を保存してからその変更が反映されるまで、どれ位かかりますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-133">If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?</span></span>

<span data-ttu-id="2f95e-134">変更が有効になるまで最大 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-134">It may take up to 1 hour for the changes to take effect.</span></span>

## <a name="is-bulk-email-filtering-automatically-enabled"></a><span data-ttu-id="2f95e-135">バルク メールのフィルタリングは自動的に有効になりますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-135">Is bulk email filtering automatically enabled?</span></span>

<span data-ttu-id="2f95e-136">はい。</span><span class="sxs-lookup"><span data-stu-id="2f95e-136">Yes.</span></span> <span data-ttu-id="2f95e-137">バルクメールの詳細については、「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-137">For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

## <a name="does-the-service-provide-url-filtering"></a><span data-ttu-id="2f95e-138">このサービスでは URL フィルター機能が提供されますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-138">Does the service provide URL filtering?</span></span>

<span data-ttu-id="2f95e-139">はい。このサービスには、メッセージ内の Url を確認する URL フィルターがあります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-139">Yes, the service has a URL filter that checks for URLs within messages.</span></span> <span data-ttu-id="2f95e-140">既知のスパムまたは悪意のあるコンテンツに関連付けられた Url が検出されると、そのメッセージはスパムとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-140">If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a><span data-ttu-id="2f95e-141">サービス使用中の顧客が Microsoft へ偽陰性 (スパム) メッセージおよび偽陽性 (スパムでない) メッセージを送信するにはどうしますか。</span><span class="sxs-lookup"><span data-stu-id="2f95e-141">How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?</span></span>

<span data-ttu-id="2f95e-142">スパムとスパムではないメッセージを分析のために Microsoft に送信するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-142">Spam and non-spam messages can be submitted to Microsoft for analysis in several ways.</span></span> <span data-ttu-id="2f95e-143">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-143">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="can-i-get-spam-reports"></a><span data-ttu-id="2f95e-144">スパム報告を取得できますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-144">Can I get spam reports?</span></span>

<span data-ttu-id="2f95e-145">はい。たとえば、Microsoft 365 管理センターでスパム検出レポートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-145">Yes, for example you can get a spam detection report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2f95e-146">このレポートでは、スパムボリュームが一意のメッセージ数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-146">This report shows spam volume as a count of unique messages.</span></span> <span data-ttu-id="2f95e-147">レポートの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-147">For more information about reporting, see the following links:</span></span>

<span data-ttu-id="2f95e-148">Exchange Online のお客様: [Exchange online での監視、レポート、メッセージ追跡](https://docs.microsoft.com/exchange/monitoring/monitoring)</span><span class="sxs-lookup"><span data-stu-id="2f95e-148">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)</span></span>

<span data-ttu-id="2f95e-149">スタンドアロン EOP のお客様: [Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)</span><span class="sxs-lookup"><span data-stu-id="2f95e-149">Standalone EOP customers: [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)</span></span>

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a><span data-ttu-id="2f95e-150">誰かがメッセージを送信しましたが、見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="2f95e-150">Someone sent me a message and I can't find it.</span></span> <span data-ttu-id="2f95e-151">スパムとして検出された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-151">I suspect that it may have been detected as spam.</span></span> <span data-ttu-id="2f95e-152">調べるためのツールはありますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-152">Is there a tool that I can use to find out?</span></span>

<span data-ttu-id="2f95e-153">はい、メッセージ追跡ツールを使用すると、電子メールメッセージがサービスを通過するときに追跡して、どのような問題が発生しているかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-153">Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them.</span></span> <span data-ttu-id="2f95e-154">メッセージ追跡ツールを使用して、メッセージがスパムとしてマークされた理由を確認する方法の詳細については、「[メッセージがスパムとしてマークされましたか?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-154">For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span></span>

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a><span data-ttu-id="2f95e-155">ユーザーがスパムを送信した場合、サービスはメールを調整 (速度制限) しますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-155">Will the service throttle (rate limit) my mail if my users send outbound spam?</span></span>

<span data-ttu-id="2f95e-156">ユーザーから特定の時間枠 (たとえば1時間) 以内にサービスを通じて送信されたメールが EOP によってスパムと判断された場合、そのユーザーはメッセージの送信をブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-156">If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by EOP, the user will be blocked from sending messages.</span></span> <span data-ttu-id="2f95e-157">この結果、通常の送信 IP プールが禁止リストに追加される可能性は減少します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-157">In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>

<span data-ttu-id="2f95e-p113">送信者が送信スパムの送信をブロックされている場合、指定したメール アドレスに通知を送信できます。 この設定の詳細については、「[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-p113">You can send a notification to a specified email address when a sender is blocked sending outbound spam. For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a><span data-ttu-id="2f95e-160">サードパーティのスパム対策およびマルウェア対策プロバイダーを Exchange Online と併用できますか。</span><span class="sxs-lookup"><span data-stu-id="2f95e-160">Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?</span></span>

<span data-ttu-id="2f95e-161">はい。</span><span class="sxs-lookup"><span data-stu-id="2f95e-161">Yes.</span></span> <span data-ttu-id="2f95e-162">MX レコードを Microsoft に指定することをお勧めしますが、Microsoft 以外の場所に電子メールをルーティングする正当な業務上の理由があることを認識しています。</span><span class="sxs-lookup"><span data-stu-id="2f95e-162">Although we recommend that you point your MX record to Microsoft, we realize that there are legitimate business reasons to route your email to somewhere other than Microsoft first.</span></span>

- <span data-ttu-id="2f95e-163">**Inbound**: サードパーティプロバイダーをポイントするように MX レコードを変更し、追加の処理のためにメッセージを EOP にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="2f95e-163">**Inbound**: Change your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing.</span></span> <span data-ttu-id="2f95e-164">詳細については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-164">For more information, see [Enhanced Filtering for connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="2f95e-165">**送信**: Microsoft 365 から送信先のサードパーティプロバイダーにスマートホストルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-165">**Outbound**: Configure smart host routing from Microsoft 365 to the destination third-party provider.</span></span>

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a><span data-ttu-id="2f95e-166">マイクロソフトには、フィッシング詐欺から自分を守る方法に関するドキュメントはありますか。</span><span class="sxs-lookup"><span data-stu-id="2f95e-166">Does Microsoft have any documentation about how I can protect myself from phishing scams?</span></span>

<span data-ttu-id="2f95e-167">はい。</span><span class="sxs-lookup"><span data-stu-id="2f95e-167">Yes.</span></span> <span data-ttu-id="2f95e-168">詳細については、「[インターネット上のプライバシーを保護](https://support.microsoft.com/help/4091455)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-168">For more information, see [Protect your privacy on the internet](https://support.microsoft.com/help/4091455)</span></span>

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a><span data-ttu-id="2f95e-169">スパム メッセージおよびマルウェア メッセージの送信元に関する調査や、法執行機関への転送は行っていますか?</span><span class="sxs-lookup"><span data-stu-id="2f95e-169">Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?</span></span>

<span data-ttu-id="2f95e-170">サービスの中心はスパムやマルウェアの検出と除去ですが、特に危険で破壊力が大きい一連のスパムまたは攻撃については、加害者を調査および追跡する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-170">The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators.</span></span> <span data-ttu-id="2f95e-171">たとえば、Microsoft の法律部門やデジタル犯罪対策部門と連携して悪意のあるボットネットを削除したり、加害者がサービスを使用できないようにしたり (そのサービスが外部への電子メール送信に使用されている場合)、刑事告発のために法執行機関に情報を提供したりします。</span><span class="sxs-lookup"><span data-stu-id="2f95e-171">This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a><span data-ttu-id="2f95e-172">メールが確実に配信されるようにするための、送信メールに関するベスト プラクティスは?</span><span class="sxs-lookup"><span data-stu-id="2f95e-172">What are a set of best outbound mailing practices that will ensure that my mail is delivered?</span></span>

<span data-ttu-id="2f95e-173">以下に示すガイドラインは、送信メール メッセージを送信するためのベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="2f95e-173">The guidelines presented below are best practices for sending outbound email messages.</span></span>

- <span data-ttu-id="2f95e-174">**ソースメールドメインが DNS で解決される必要があります。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-174">**The source email domain should resolve in DNS.**</span></span>

  <span data-ttu-id="2f95e-175">たとえば、送信者が user@fabrikam 場合、ドメイン fabrikam は IP アドレス192.0.43.10 に解決されます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-175">For example, if the sender is user@fabrikam, the domain fabrikam resolves to the IP address 192.0.43.10.</span></span>
  
  <span data-ttu-id="2f95e-176">DNS で送信者のドメインの A-record と MX レコードが存在しない場合、メッセージのコンテンツがスパムであるなしにかかわらず、サービスはより危険度の高い配信プール経由でメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="2f95e-176">If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam.</span></span> <span data-ttu-id="2f95e-177">より危険度の高い配信プールの詳細については、「[送信メッセージ用の高リスク配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f95e-177">For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="2f95e-178">**送信メールの eserver には、逆引き DNS (PTR) エントリが必要です。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-178">**Outbound mail eserver should have a reverse DNS (PTR) entry.**</span></span>

  <span data-ttu-id="2f95e-179">たとえば、電子メールの送信元 IP アドレスが192.0.43.10 の場合、逆引き DNS エントリはになり `43-10.any.icann.org` ます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-179">For example, if the email source IP address is 192.0.43.10, the reverse DNS entry would be `43-10.any.icann.org`.\`</span></span>

- <span data-ttu-id="2f95e-180">**HELO/EHLO および MAIL FROM コマンドに整合性があり、IP アドレスではなくドメイン名の形式で表現される必要があります。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-180">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>

  <span data-ttu-id="2f95e-181">HELO/EHLO コマンドは送信 IP アドレスの逆引き DNS と一致するように構成する必要があります。このようにすることで、メッセージ ヘッダーのあらゆる部分でドメインが同一に保たれます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-181">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>

- <span data-ttu-id="2f95e-182">**適切な SPF レコードが DNS に設定されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-182">**Ensure that proper SPF records are set up in DNS.**</span></span>

  <span data-ttu-id="2f95e-p119">SPF レコードとは、ドメインから送信されたメールがそのドメインから実際に送信されていること、なりすましではないことを確認するためのメカニズムです。 SPF レコードの詳細については、以下のリンクを参照してください:</span><span class="sxs-lookup"><span data-stu-id="2f95e-p119">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>

  [<span data-ttu-id="2f95e-185">SPF を設定して、スプーフィングを防止する</span><span class="sxs-lookup"><span data-stu-id="2f95e-185">Set up SPF to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [<span data-ttu-id="2f95e-186">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="2f95e-186">Domains FAQ</span></span>](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- <span data-ttu-id="2f95e-187">**DKIM で電子メールを署名する場合、relaxed 正規化で署名します。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-187">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>

  <span data-ttu-id="2f95e-p120">送信者が Domain Keys Identified Mail (DKIM) を使用してメッセージに署名し、サービスを通じて送信メールを送信する場合、送信者は relaxed ヘッダー正規化アルゴリズムを使用して署名する必要があります。 strict ヘッダー正規化で署名することにより、メッセージがサービスを通過するときに署名が無効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-p120">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>

- <span data-ttu-id="2f95e-190">**ドメイン所有者は、WHOIS データベースに正確な情報が必要です。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-190">**Domain owners should have accurate information in the WHOIS database.**</span></span>

  <span data-ttu-id="2f95e-191">これにより、安定した親会社、連絡先、およびネーム サーバーを入力することで、ドメインの所有者と問い合わせ方法が特定されます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-191">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>

- <span data-ttu-id="2f95e-192">**バルク メール業者にとって、From: 名は メッセージの送信者を表し、メッセージの件名行はメッセージの内容の概要である必要があります。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-192">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>

  <span data-ttu-id="2f95e-p121">メッセージの本文は、提供、サービス、製品の分かりやすい説明である必要があります。 たとえば、送信者が Contoso 会社のバルク メールを送信している場合、電子メールの差出人および件名は以下のようになります:</span><span class="sxs-lookup"><span data-stu-id="2f95e-p121">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>

  > <span data-ttu-id="2f95e-195">From: marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f95e-195">From: marketing@contoso.com</span></span> <br/> <span data-ttu-id="2f95e-196">件名: クリスマス シーズンの最新カタログ!</span><span class="sxs-lookup"><span data-stu-id="2f95e-196">Subject: New updated catalog for the Christmas season!</span></span>

  <span data-ttu-id="2f95e-197">以下の例は説明的ではないため、バルク メールとしては不適切です。</span><span class="sxs-lookup"><span data-stu-id="2f95e-197">The following is an example of what not to do because it is not descriptive:</span></span>

  > <span data-ttu-id="2f95e-198">From: user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="2f95e-198">From: user@hotmail.com</span></span> <br/> <span data-ttu-id="2f95e-199">件名: カタログ</span><span class="sxs-lookup"><span data-stu-id="2f95e-199">Subject: Catalogs</span></span>

- <span data-ttu-id="2f95e-200">**バルク メールが多数の受信者に送信されるもので、メッセージが広報形式である場合、メッセージの最下部に登録解除手段が存在する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-200">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>

  <span data-ttu-id="2f95e-201">登録解除オプションは次のように表示されるはずです:</span><span class="sxs-lookup"><span data-stu-id="2f95e-201">The unsubscribe option should resemble the following:</span></span>

  > <span data-ttu-id="2f95e-202">このメッセージは、sender@fabrikam.com から example@contoso.com に送信されました。</span><span class="sxs-lookup"><span data-stu-id="2f95e-202">This message was sent to example@contoso.com by sender@fabrikam.com.</span></span> <span data-ttu-id="2f95e-203">プロファイルの更新/メールアドレス |**Safeunsubscribe**を使用した即時削除 &trade; |プライバシーポリシー</span><span class="sxs-lookup"><span data-stu-id="2f95e-203">Update Profile/Email Address | Instant removal with **SafeUnsubscribe**&trade; | Privacy Policy</span></span>

- <span data-ttu-id="2f95e-204">**バルク メールを送信する場合、ダブル オプトインを使用してリスト取得を実行する必要があります。バルク メールの送信者にとって、ダブル オプトインは業界のベスト プラクティスです。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-204">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>

  <span data-ttu-id="2f95e-205">ダブル オプトインでは、ユーザーがマーケティング メールの会員になるには、2 つのアクションを実行する必要があります:</span><span class="sxs-lookup"><span data-stu-id="2f95e-205">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>

  1. <span data-ttu-id="2f95e-206">1 回目は、ユーザーが以前にオンではなかったチェックボックスをクリックすることにより、ユーザーが業者からの広告やメール メッセージを今後も受け取ることを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-206">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>

  2. <span data-ttu-id="2f95e-207">2 回目は、ユーザーが入力したメール アドレスに確認メールを業者が送信します。この確認メールにある時間制限付きリンクをユーザーがクリックすることにより、確認が完了します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-207">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>

  <span data-ttu-id="2f95e-208">ダブル オプトインを使用することで、バルク メール送信業者としての良好な評価を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="2f95e-208">Using double opt-in builds a good reputation for bulk email senders.</span></span>

- <span data-ttu-id="2f95e-209">**バルク送信業者は、説明責任を負うことが可能な透過的コンテンツを作成する必要があります:**</span><span class="sxs-lookup"><span data-stu-id="2f95e-209">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>

  1. <span data-ttu-id="2f95e-210">アドレス帳に送信者を追加するようメール受信者に何度もお願いしても、それがメールの配信を保証しないことは明らかです。</span><span class="sxs-lookup"><span data-stu-id="2f95e-210">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>

  2. <span data-ttu-id="2f95e-211">メッセージ本文でリダイレクトを作成するときには、一貫したリンク スタイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-211">When constructing redirects in the body of the message, use a consistent link style.</span></span>

  3. <span data-ttu-id="2f95e-212">サイズの大きな画像や添付ファイル、画像だけのメッセージは送信しません。</span><span class="sxs-lookup"><span data-stu-id="2f95e-212">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>

  4. <span data-ttu-id="2f95e-213">トラッキング ピクセル (Web バグ、ビーコン) を使用する場合には、プライバシー ポリシー、P3P 設定にトラッキング ピクセルが存在することを明記します。</span><span class="sxs-lookup"><span data-stu-id="2f95e-213">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>

- <span data-ttu-id="2f95e-214">**送信バウンスメッセージを書式設定します。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-214">**Format outbound bounce messages.**</span></span>

  <span data-ttu-id="2f95e-215">配信状態通知メッセージ (配信不能レポート、Ndr、またはバウンスメッセージとも呼ばれる) を生成する場合、送信者は、 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)で指定されているようにバウンスの形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-215">When generating delivery status notification messages (also known as non-delivery reports, NDRs, or bounce messages), senders should follow the format of a bounce as specified in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).</span></span>

- <span data-ttu-id="2f95e-216">**存在しないユーザーのバウンスされたメール アドレスを削除します。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-216">**Remove bounced email addresses for non-existent users.**</span></span>

  <span data-ttu-id="2f95e-p123">メール アドレスが使用されていないことを示す NDR を受信したら、存在しないメール エイリアスを一覧から削除します。 メール アドレスは時間とともに変化し、ユーザーはメール アドレスを破棄することがあります。</span><span class="sxs-lookup"><span data-stu-id="2f95e-p123">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>

- <span data-ttu-id="2f95e-219">**Hotmail の Smart Network Data Services (SNDS) プログラムを使用します。**</span><span class="sxs-lookup"><span data-stu-id="2f95e-219">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>

  <span data-ttu-id="2f95e-p124">Hotmail は Smart Network Data Services というプログラムを使用します。このプログラムにより、送信業者はエンド ユーザーが送信したクレームをチェックできます。 SNDS は、Hotmail の配信の問題をトラブルシューティングするための第一のポータルです。</span><span class="sxs-lookup"><span data-stu-id="2f95e-p124">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>
