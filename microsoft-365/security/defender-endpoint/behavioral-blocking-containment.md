---
title: 動作ブロックと封じ込め
description: Microsoft Defender for Endpoint での動作のブロックと格納機能について説明します。
keywords: Microsoft Defender for Endpoint,EDRモードでのサポート、パッシブ モードのブロック
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 98ea631536bbfa9e1858f70ae3a0ea9de8743572
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029779"
---
# <a name="behavioral-blocking-and-containment"></a><span data-ttu-id="c93e2-104">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="c93e2-104">Behavioral blocking and containment</span></span>

<span data-ttu-id="c93e2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c93e2-105">**Applies to:**</span></span>
- [<span data-ttu-id="c93e2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c93e2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c93e2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c93e2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c93e2-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c93e2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c93e2-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c93e2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="c93e2-110">概要</span><span class="sxs-lookup"><span data-stu-id="c93e2-110">Overview</span></span>

<span data-ttu-id="c93e2-111">今日の脅威の状況は、ファイルレス[](/windows/security/threat-protection/intelligence/fileless-threats)マルウェアによって過剰に実行され、土地から離れ、従来のソリューションよりも高速に変化する高度な多態性の脅威、および侵害されたデバイスで敵が見つけたものに適応する人が操作する攻撃です。</span><span class="sxs-lookup"><span data-stu-id="c93e2-111">Today's threat landscape is overrun by [fileless malware](/windows/security/threat-protection/intelligence/fileless-threats) and that lives off the land, highly polymorphic threats that mutate faster than traditional solutions can keep up with, and human-operated attacks that adapt to what adversaries find on compromised devices.</span></span> <span data-ttu-id="c93e2-112">従来のセキュリティ ソリューションでは、このような攻撃を止めるには十分ではありません。Defender for Endpoint に含まれる、動作のブロックや格納などの、人工知能 (AI) とデバイス学習 (ML) のサポート機能[が必要です](/windows/security)。</span><span class="sxs-lookup"><span data-stu-id="c93e2-112">Traditional security solutions are not sufficient to stop such attacks; you need artificial intelligence (AI) and device learning (ML) backed capabilities, such as behavioral blocking and containment, included in [Defender for Endpoint](/windows/security).</span></span>

<span data-ttu-id="c93e2-113">動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作とプロセス ツリーに基づいて、脅威を特定して停止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-113">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> <span data-ttu-id="c93e2-114">次世代の保護、EDR、Defender for Endpoint のコンポーネントと機能は、動作ブロック機能と格納機能で機能します。</span><span class="sxs-lookup"><span data-stu-id="c93e2-114">Next-generation protection, EDR, and Defender for Endpoint components and features work together in behavioral blocking and containment capabilities.</span></span>

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="動作ブロックと封じ込め":::

<span data-ttu-id="c93e2-116">動作のブロックと格納機能は、Defender for Endpoint の複数のコンポーネントと機能と組み合わせ、攻撃を直ちに停止し、攻撃の進行を防止します。</span><span class="sxs-lookup"><span data-stu-id="c93e2-116">Behavioral blocking and containment capabilities work with multiple components and features of Defender for Endpoint to stop attacks immediately and prevent attacks from progressing.</span></span>

- <span data-ttu-id="c93e2-117">[次世代の保護](microsoft-defender-antivirus-in-windows-10.md)(Microsoft Defender ウイルス対策を含む) は、動作を分析して脅威を検出し、実行を開始した脅威を停止できます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-117">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md) (which includes Microsoft Defender Antivirus) can detect threats by analyzing behaviors, and stop threats that have started running.</span></span>

- <span data-ttu-id="c93e2-118">[エンドポイントの検出と応答](overview-endpoint-detection-response.md)(EDR) は、ネットワーク、デバイス、カーネルの動作全体でセキュリティ信号を受信します。</span><span class="sxs-lookup"><span data-stu-id="c93e2-118">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) receives security signals across your network, devices, and kernel behavior.</span></span> <span data-ttu-id="c93e2-119">脅威が検出されると、アラートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-119">As threats are detected, alerts are created.</span></span> <span data-ttu-id="c93e2-120">同じ種類の複数のアラートがインシデントに集約され、セキュリティ運用チームが調査して対応しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c93e2-120">Multiple alerts of the same type are aggregated into incidents, which makes it easier for your security operations team to investigate and respond.</span></span>

- <span data-ttu-id="c93e2-121">[Defender for Endpoint](overview-endpoint-detection-response.md)には、EDR を介して受信したネットワーク、エンドポイント、カーネルの動作信号に加えて、ID、電子メール、データ、アプリにわたるさまざまな光学機能があります。</span><span class="sxs-lookup"><span data-stu-id="c93e2-121">[Defender for Endpoint](overview-endpoint-detection-response.md) has a wide range of optics across identities, email, data, and apps, in addition to the network, endpoint, and kernel behavior signals received through EDR.</span></span> <span data-ttu-id="c93e2-122">Microsoft 365 Defender [、Defender](../defender/microsoft-365-defender.md)for Endpoint のコンポーネントは、これらの信号を処理して関連付け、検出アラートを発生し、インシデントに関連するアラートを接続します。</span><span class="sxs-lookup"><span data-stu-id="c93e2-122">A component of [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender for Endpoint processes and correlates these signals, raises detection alerts, and connects related alerts in incidents.</span></span>

<span data-ttu-id="c93e2-123">これらの機能を使用すると、実行を開始した場合でも、より多くの脅威を防止またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-123">With these capabilities, more threats can be prevented or blocked, even if they start running.</span></span> <span data-ttu-id="c93e2-124">疑わしい動作が検出されると、脅威が含まれる、アラートが作成され、脅威は追跡で停止されます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-124">Whenever suspicious behavior is detected, the threat is contained, alerts are created, and threats are stopped in their tracks.</span></span>

<span data-ttu-id="c93e2-125">次の図は、動作ブロックと格納機能によってトリガーされたアラートの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="c93e2-125">The following image shows an example of an alert that was triggered by behavioral blocking and containment capabilities:</span></span>

:::image type="content" source="images/blocked-behav-alert.png" alt-text="動作のブロックと格納によるアラートの例":::

## <a name="components-of-behavioral-blocking-and-containment"></a><span data-ttu-id="c93e2-127">動作のブロックと格納のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="c93e2-127">Components of behavioral blocking and containment</span></span>

- <span data-ttu-id="c93e2-128">**クライアント上のポリシー駆動型攻撃 [表面の縮小ルール](attack-surface-reduction.md)** 定義済みの一般的な攻撃動作は、攻撃表面の縮小ルールに従って実行されません。</span><span class="sxs-lookup"><span data-stu-id="c93e2-128">**On-client, policy-driven [attack surface reduction rules](attack-surface-reduction.md)** Predefined common attack behaviors are prevented from executing, according to your attack surface reduction rules.</span></span> <span data-ttu-id="c93e2-129">このような動作を実行しようとすると、通知通知としてMicrosoft 365 Defender <https://security.microsoft.com> 表示されます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-129">When such behaviors attempt to execute, they can be seen in Microsoft 365 Defender <https://security.microsoft.com> as informational alerts.</span></span> <span data-ttu-id="c93e2-130">攻撃表面の縮小ルールは既定では有効になっていません。でポリシーを構成[Microsoft 365 Defender。](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c93e2-130">Attack surface reduction rules are not enabled by default; you configure your policies in the [Microsoft 365 Defender](microsoft-defender-security-center.md).</span></span>

- <span data-ttu-id="c93e2-131">**[クライアントの動作のブロック](client-behavioral-blocking.md)** エンドポイント上の脅威は機械学習によって検出され、ブロックされ、自動的に修復されます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-131">**[Client behavioral blocking](client-behavioral-blocking.md)** Threats on endpoints are detected through machine learning, and then are blocked and remediated automatically.</span></span> <span data-ttu-id="c93e2-132">(クライアントの動作ブロックは既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="c93e2-132">(Client behavioral blocking is enabled by default.)</span></span>

- <span data-ttu-id="c93e2-133">**[フィードバック ループブロック](feedback-loop-blocking.md)** (高速保護とも呼ばれます) 脅威検出は、行動インテリジェンスを通じて観察されます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-133">**[Feedback-loop blocking](feedback-loop-blocking.md)** (also referred to as rapid protection) Threat detections are observed through behavioral intelligence.</span></span> <span data-ttu-id="c93e2-134">脅威は停止され、他のエンドポイントで実行されません。</span><span class="sxs-lookup"><span data-stu-id="c93e2-134">Threats are stopped and prevented from running on other endpoints.</span></span> <span data-ttu-id="c93e2-135">(フィードバック ループのブロックは既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="c93e2-135">(Feedback-loop blocking is enabled by default.)</span></span>

- <span data-ttu-id="c93e2-136">**[ブロック モードでのエンドポイントEDR応答 (EDR)](edr-in-block-mode.md)** 侵害後の保護によって観察される悪意のあるアーティファクトや動作はブロックされ、含まれる。</span><span class="sxs-lookup"><span data-stu-id="c93e2-136">**[Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md)** Malicious artifacts or behaviors that are observed through post-breach protection are blocked and contained.</span></span> <span data-ttu-id="c93e2-137">EDRウイルス対策ソリューションではない場合でも、ブロック モードMicrosoft Defender ウイルス対策機能します。</span><span class="sxs-lookup"><span data-stu-id="c93e2-137">EDR in block mode works even if Microsoft Defender Antivirus is not the primary antivirus solution.</span></span> <span data-ttu-id="c93e2-138">(EDRモードの設定は既定では有効になっていません。既定では有効Microsoft 365 Defender)。</span><span class="sxs-lookup"><span data-stu-id="c93e2-138">(EDR in block mode is not enabled by default; you turn it on in Microsoft 365 Defender.)</span></span>

<span data-ttu-id="c93e2-139">Microsoft は引き続き脅威保護の機能を向上させるので、行動のブロックと格納の領域でさらに多くのことを期待してください。</span><span class="sxs-lookup"><span data-stu-id="c93e2-139">Expect more to come in the area of behavioral blocking and containment, as Microsoft continues to improve threat protection features and capabilities.</span></span> <span data-ttu-id="c93e2-140">今計画されている計画と展開を確認するには、次のロードマップを[Microsoft 365してください](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="c93e2-140">To see what's planned and rolling out now, visit the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a><span data-ttu-id="c93e2-141">動作ブロックとアクション内の格納の例</span><span class="sxs-lookup"><span data-stu-id="c93e2-141">Examples of behavioral blocking and containment in action</span></span>

<span data-ttu-id="c93e2-142">動作のブロックと封じ込め機能によって、次のような攻撃者の手法がブロックされています。</span><span class="sxs-lookup"><span data-stu-id="c93e2-142">Behavioral blocking and containment capabilities have blocked attacker techniques such as the following:</span></span>

- <span data-ttu-id="c93e2-143">LSASS からの資格情報のダンプ</span><span class="sxs-lookup"><span data-stu-id="c93e2-143">Credential dumping from LSASS</span></span>
- <span data-ttu-id="c93e2-144">プロセス間の挿入</span><span class="sxs-lookup"><span data-stu-id="c93e2-144">Cross-process injection</span></span>
- <span data-ttu-id="c93e2-145">プロセスの空洞化</span><span class="sxs-lookup"><span data-stu-id="c93e2-145">Process hollowing</span></span>
- <span data-ttu-id="c93e2-146">ユーザー アカウント制御のバイパス</span><span class="sxs-lookup"><span data-stu-id="c93e2-146">User Account Control bypass</span></span>
- <span data-ttu-id="c93e2-147">ウイルス対策の改ざん (無効にする、マルウェアを除外として追加するなど)</span><span class="sxs-lookup"><span data-stu-id="c93e2-147">Tampering with antivirus (such as disabling it or adding the malware as exclusion)</span></span>
- <span data-ttu-id="c93e2-148">ペイロードをダウンロードするコマンドとコントロール (C&C) への連絡</span><span class="sxs-lookup"><span data-stu-id="c93e2-148">Contacting Command and Control (C&C) to download payloads</span></span>
- <span data-ttu-id="c93e2-149">コイン マイニング</span><span class="sxs-lookup"><span data-stu-id="c93e2-149">Coin mining</span></span>
- <span data-ttu-id="c93e2-150">ブート レコードの変更</span><span class="sxs-lookup"><span data-stu-id="c93e2-150">Boot record modification</span></span>
- <span data-ttu-id="c93e2-151">ハッシュパス攻撃</span><span class="sxs-lookup"><span data-stu-id="c93e2-151">Pass-the-hash attacks</span></span>
- <span data-ttu-id="c93e2-152">ルート証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="c93e2-152">Installation of root certificate</span></span>
- <span data-ttu-id="c93e2-153">さまざまな脆弱性に対する悪用の試み</span><span class="sxs-lookup"><span data-stu-id="c93e2-153">Exploitation attempt for various vulnerabilities</span></span>

<span data-ttu-id="c93e2-154">以下に、実際の動作ブロックとイントメントの 2 つの実際の例を示します。</span><span class="sxs-lookup"><span data-stu-id="c93e2-154">Below are two real-life examples of behavioral blocking and containment in action.</span></span>

### <a name="example-1-credential-theft-attack-against-100-organizations"></a><span data-ttu-id="c93e2-155">例 1: 100 組織に対する資格情報の盗難攻撃</span><span class="sxs-lookup"><span data-stu-id="c93e2-155">Example 1: Credential theft attack against 100 organizations</span></span>

<span data-ttu-id="c93e2-156">「AI[](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)による行動ベースのブロックは、追跡中の攻撃を停止する」で説明したように、世界中の 100 の組織に対する資格情報の盗難攻撃は、行動ブロックと格納機能によって停止されました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-156">As described in [In hot pursuit of elusive threats: AI-driven behavior-based blocking stops attacks in their tracks](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks), a credential theft attack against 100 organizations around the world was stopped by behavioral blocking and containment capabilities.</span></span> <span data-ttu-id="c93e2-157">ルアー ドキュメントを含むスピア フィッシングメール メッセージが、対象の組織に送信されました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-157">Spear-phishing email messages that contained a lure document were sent to the targeted organizations.</span></span> <span data-ttu-id="c93e2-158">受信者が添付ファイルを開いた場合、関連するリモート ドキュメントはユーザーのデバイスでコードを実行し、Lokibot マルウェアを読み込む事ができた。これは資格情報を盗み、盗まれたデータを汚し、コマンド アンド コントロール サーバーからのさらなる指示を待った。</span><span class="sxs-lookup"><span data-stu-id="c93e2-158">If a recipient opened the attachment, a related remote document was able to execute code on the user's device and load Lokibot malware, which stole credentials, exfiltrated stolen data, and waited for further instructions from a command-and-control server.</span></span>

<span data-ttu-id="c93e2-159">Defender for Endpoint の動作ベースのデバイス学習モデルは、攻撃チェーンの 2 つのポイントで攻撃者の手法をキャッチして停止しました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-159">Behavior-based device learning models in Defender for Endpoint caught and stopped the attacker's techniques at two points in the attack chain:</span></span>

- <span data-ttu-id="c93e2-160">最初の保護層が悪用の動作を検出しました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-160">The first protection layer detected the exploit behavior.</span></span> <span data-ttu-id="c93e2-161">クラウド内のデバイス学習分類子は、脅威を正しく識別し、すぐにクライアント デバイスに攻撃をブロックするように指示しました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-161">Device learning classifiers in the cloud correctly identified the threat as and immediately instructed the client device to block the attack.</span></span>
- <span data-ttu-id="c93e2-162">2 番目の保護層は、攻撃が最初のレイヤーを越え、プロセスの空きを検出し、そのプロセスを停止し、対応するファイル (Lokibot など) を削除した場合の停止に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-162">The second protection layer, which helped stop cases where the attack got past the first layer, detected process hollowing, stopped that process, and removed the corresponding files (such as Lokibot).</span></span>

<span data-ttu-id="c93e2-163">攻撃が検出および停止されている間に、"初期アクセスアラート" などのアラートがトリガーされ[、Microsoft 365 Defender](microsoft-defender-security-center.md)ポータル (以前は Microsoft Defender セキュリティ センター) に表示されました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-163">While the attack was detected and stopped, alerts, such as an "initial access alert," were triggered and appeared in the [Microsoft 365 Defender portal](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center):</span></span>

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="ポータルでの初期アクセスMicrosoft 365 Defender通知":::

<span data-ttu-id="c93e2-165">次の使用例は、クラウド内の動作ベースのデバイス学習モデルが、実行を開始した後でも、攻撃に対する新しい保護層を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c93e2-165">This example shows how behavior-based device learning models in the cloud add new layers of protection against attacks, even after they have started running.</span></span>

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a><span data-ttu-id="c93e2-166">例 2: NTLM リレー - ジューシー ポテト マルウェアバリアント</span><span class="sxs-lookup"><span data-stu-id="c93e2-166">Example 2: NTLM relay - Juicy Potato malware variant</span></span>

<span data-ttu-id="c93e2-167">最近のブログ投稿「ビヘイビアーブロック[](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)と格納: 光学を保護に変換する」で説明したように、2020 年 1 月に Defender for Endpoint は組織内のデバイスで特権エスカレーション アクティビティを検出しました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-167">As described in the recent blog post, [Behavioral blocking and containment: Transforming optics into protection](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection), in January 2020, Defender for Endpoint detected a privilege escalation activity on a device in an organization.</span></span> <span data-ttu-id="c93e2-168">"NTLM リレーを使用した特権エスカレーションの可能性" というアラートがトリガーされました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-168">An alert called "Possible privilege escalation using NTLM relay" was triggered.</span></span>

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="ジューシー ジャガイモ マルウェアに関する NTLM アラート":::

<span data-ttu-id="c93e2-170">脅威はマルウェアである判明しました。これは、デバイスの特権エスカレーションを取得するために攻撃者によって使用される、ジュート ポテトと呼ばれる悪名高いハッキング ツールの新しい、前に見られないバリアントでした。</span><span class="sxs-lookup"><span data-stu-id="c93e2-170">The threat turned out to be malware; it was a new, not-seen-before variant of a notorious hacking tool called Juicy Potato, which is used by attackers to get privilege escalation on a device.</span></span>

<span data-ttu-id="c93e2-171">アラートがトリガーされた数分後、ファイルが分析され、悪意のあるものに確認されました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-171">Minutes after the alert was triggered, the file was analyzed, and confirmed to be malicious.</span></span> <span data-ttu-id="c93e2-172">次の図に示すように、プロセスは停止およびブロックされました。</span><span class="sxs-lookup"><span data-stu-id="c93e2-172">Its process was stopped and blocked, as shown in the following image:</span></span>

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="アーティファクトがブロックされている":::

<span data-ttu-id="c93e2-174">アーティファクトがブロックされた数分後、同じデバイス上で同じファイルの複数のインスタンスがブロックされ、追加の攻撃者や他のマルウェアがデバイスに展開されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="c93e2-174">A few minutes after the artifact was blocked, multiple instances of the same file were blocked on the same device, preventing additional attackers or other malware from deploying on the device.</span></span>

<span data-ttu-id="c93e2-175">この例では、動作のブロックと封じ込め機能を使用すると、脅威が検出され、格納され、自動的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c93e2-175">This example shows that with behavioral blocking and containment capabilities, threats are detected, contained, and blocked automatically.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c93e2-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="c93e2-176">Next steps</span></span>

- [<span data-ttu-id="c93e2-177">Defender for Endpoint の詳細</span><span class="sxs-lookup"><span data-stu-id="c93e2-177">Learn more about Defender for Endpoint</span></span>](overview-endpoint-detection-response.md)

- [<span data-ttu-id="c93e2-178">攻撃表面の縮小ルールを構成する</span><span class="sxs-lookup"><span data-stu-id="c93e2-178">Configure your attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="c93e2-179">ブロック モードEDR有効にする</span><span class="sxs-lookup"><span data-stu-id="c93e2-179">Enable EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="c93e2-180">最近のグローバル脅威アクティビティを確認する</span><span class="sxs-lookup"><span data-stu-id="c93e2-180">See recent global threat activity</span></span>](https://www.microsoft.com/wdsi/threats)

- [<span data-ttu-id="c93e2-181">アプリケーションの概要をMicrosoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c93e2-181">Get an overview of Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)
