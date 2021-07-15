---
title: 異常検出アラートを調査する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 異常検出アラートを調査する。
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420471"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="5ed75-103">異常検出アラートを調査する</span><span class="sxs-lookup"><span data-stu-id="5ed75-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="5ed75-104">Microsoft アプリ ガバナンスでは、悪意のあるアクティビティに対するセキュリティ検出とアラートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="5ed75-105">このガイドの目的は、調査と修復のタスクを支援するために、各アラートについての一般的で実用的な情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="5ed75-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="5ed75-106">このガイドに記載されているのは、アラートがトリガーされる条件に関する一般的な情報です。</span><span class="sxs-lookup"><span data-stu-id="5ed75-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="5ed75-107">異常検出は本質的に不明確であるため、標準とは異なる動作が発生した場合にのみトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="5ed75-108">最後に、一部のアラートはプレビュー段階である可能性があるため、定期的に公式ドキュメントで更新されたアラートの状態を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5ed75-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="5ed75-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="5ed75-109">MITRE ATT&CK</span></span>

<span data-ttu-id="5ed75-110">Microsoft アプリ ガバナンス アラートとよく知られた MITRE ATT&CK マトリックスとの間の関係を簡単にマップできるよう、MITRE ATT&CK の対応する方策ごとにアラートを分類しました。</span><span class="sxs-lookup"><span data-stu-id="5ed75-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="5ed75-111">この追加の参照により、Microsoft アプリケーションのセキュリティとガバナンス アラートがトリガーされたときに使用されている可能性のある疑わしい攻撃手法を容易に把握できます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="5ed75-112">このガイドでは、次のカテゴリの Microsoft アプリ ガバナンス アラートの調査と修復に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="5ed75-113">初期アクセス</span><span class="sxs-lookup"><span data-stu-id="5ed75-113">Initial Access</span></span>
- <span data-ttu-id="5ed75-114">実行</span><span class="sxs-lookup"><span data-stu-id="5ed75-114">Execution</span></span>
- <span data-ttu-id="5ed75-115">永続性</span><span class="sxs-lookup"><span data-stu-id="5ed75-115">Persistence</span></span>
- <span data-ttu-id="5ed75-116">特権エスカレーション</span><span class="sxs-lookup"><span data-stu-id="5ed75-116">Privilege Escalation</span></span>
- <span data-ttu-id="5ed75-117">防御回避</span><span class="sxs-lookup"><span data-stu-id="5ed75-117">Defense Evasion</span></span>
- <span data-ttu-id="5ed75-118">資格情報へのアクセス</span><span class="sxs-lookup"><span data-stu-id="5ed75-118">Credential Access</span></span>
- <span data-ttu-id="5ed75-119">コレクション</span><span class="sxs-lookup"><span data-stu-id="5ed75-119">Collection</span></span>
- <span data-ttu-id="5ed75-120">流出</span><span class="sxs-lookup"><span data-stu-id="5ed75-120">Exfiltration</span></span>
- <span data-ttu-id="5ed75-121">影響</span><span class="sxs-lookup"><span data-stu-id="5ed75-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="5ed75-122">セキュリティ アラートの分類</span><span class="sxs-lookup"><span data-stu-id="5ed75-122">Security alert classifications</span></span>

<span data-ttu-id="5ed75-123">適切な調査に従って、すべての Microsoft アプリ ガバナンス アラートは、次のアクティビティの種類のいずれかとして分類することができます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="5ed75-124">真陽性 (TP): 悪意が確認されたアクティビティに関するアラート。</span><span class="sxs-lookup"><span data-stu-id="5ed75-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="5ed75-125">問題のない真陽性: 侵入テストや他の承認された疑わしいアクションなど、疑わしいが悪意のないアクティビティに関するアラート。</span><span class="sxs-lookup"><span data-stu-id="5ed75-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="5ed75-126">偽陽性 (FP): 悪意のないアクティビティに関するアラート。</span><span class="sxs-lookup"><span data-stu-id="5ed75-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="5ed75-127">一般的な調査手順</span><span class="sxs-lookup"><span data-stu-id="5ed75-127">General investigation steps</span></span>

<span data-ttu-id="5ed75-128">推奨アクションを適用する前に、潜在的な脅威をより明確に理解するためにアラートの種類を調査するとき、次の一般的なガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="5ed75-129">アプリの重大度レベルを確認し、テナント内の他のアプリと比較します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="5ed75-130">確認は、最も大きなリスクをもたらすテナント内のアプリを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="5ed75-131">TP を識別する場合は、アプリのすべてのアクティビティを確認して、その影響について理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="5ed75-132">たとえば、次のアプリ情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="5ed75-133">付与されているアクセス権のスコープ</span><span class="sxs-lookup"><span data-stu-id="5ed75-133">Scopes granted access</span></span>
  - <span data-ttu-id="5ed75-134">異常な動作</span><span class="sxs-lookup"><span data-stu-id="5ed75-134">Unusual behavior</span></span>  
  - <span data-ttu-id="5ed75-135">IP アドレスと場所</span><span class="sxs-lookup"><span data-stu-id="5ed75-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="5ed75-136">初期アクセス アラート</span><span class="sxs-lookup"><span data-stu-id="5ed75-136">Initial access alerts</span></span>

<span data-ttu-id="5ed75-137">このセクションでは、悪意のあるアプリが組織への足掛かりを得ようとしている可能性があることを示すアラートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="5ed75-138">疑わしいコンテンツ スコープのエンコードされたアプリ名</span><span class="sxs-lookup"><span data-stu-id="5ed75-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="5ed75-139">**重要度:** 中</span><span class="sxs-lookup"><span data-stu-id="5ed75-139">**Severity:** Medium</span></span>

<span data-ttu-id="5ed75-140">**説明**: この検出により、疑わしいコンテンツ スコープに要求され、Graph API を介してユーザーのメール フォルダーにアクセスした、Unicode またはエンコードされた文字などが使用されている OAuth アプリが示されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="5ed75-141">このアラートは、攻撃者がユーザーに誤解を与えて悪意のあるアプリに同意させることができるように、悪意のあるアプリを既知の信頼できるアプリとしてカモフラージュさせようとしていることを示す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ed75-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="5ed75-142">**TP または FP?**</span><span class="sxs-lookup"><span data-stu-id="5ed75-142">**TP or FP?**</span></span>

- <span data-ttu-id="5ed75-143">**TP**: OAuth アプリが不明なソースから配信された疑わしいスコープで表示名をエンコードしたことを確認できる場合、真陽性が示されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="5ed75-144">**推奨されるアクション**: このアプリによって要求されたアクセス許可のレベルと、アクセスを許可したユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="5ed75-145">調査に基づいて、このアプリへのアクセスの禁止を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="5ed75-146">アプリへのアクセスを禁止するには、 [OAuth アプリ] ページで、禁止するアプリが表示されている行の禁止アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="5ed75-147">自分がインストールして承認したアプリが禁止されたことをユーザーに通知するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="5ed75-148">その通知により、ユーザーは、アプリが無効になり、接続されているアプリにアクセスできなくなることがわかります。</span><span class="sxs-lookup"><span data-stu-id="5ed75-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="5ed75-149">ユーザーに知らせたくない場合は、ダイアログの [この禁止されたアプリにアクセス許可を付与したユーザーに通知を送信します] の選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="5ed75-150">アプリが使用禁止になることをアプリのユーザーに知らせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ed75-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="5ed75-151">**FP**: アプリの名前は誤解を与える可能性があるが、組織での正当なビジネス上の使用であることを確認した場合。</span><span class="sxs-lookup"><span data-stu-id="5ed75-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="5ed75-152">**推奨されるアクション**: アラートを無視します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="5ed75-153">攻撃対象を理解する</span><span class="sxs-lookup"><span data-stu-id="5ed75-153">Understand the scope of the breach</span></span>

<span data-ttu-id="5ed75-154">[危険な OAuth アプリを調査する](/cloud-app-security/investigate-risky-oauth)方法についてのチュートリアルに従います。</span><span class="sxs-lookup"><span data-stu-id="5ed75-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="5ed75-155">読み取りスコープを持つ OAuth アプリに疑わしい応答 URL がある</span><span class="sxs-lookup"><span data-stu-id="5ed75-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="5ed75-156">**重要度**: 中</span><span class="sxs-lookup"><span data-stu-id="5ed75-156">**Severity**: Medium</span></span>

<span data-ttu-id="5ed75-157">**説明**: この検出により、Graph API を介した User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared などによる疑わしい応答 URL へのリダイレクトの読み取りスコープのみを持つ OAuth アプリが示されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="5ed75-158">このアクティビティは、特権の少ないアクセス許可 (読み取りスコープなど) を持つ悪意のあるアプリがユーザー アカウントの偵察に悪用できることを示すことを試みます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="5ed75-159">**TP または FP?**</span><span class="sxs-lookup"><span data-stu-id="5ed75-159">**TP or FP?**</span></span>

- <span data-ttu-id="5ed75-160">**TP**: 読み取りスコープを持つ OAuth アプリが不明なソースから配信されており、疑わしい URL にリダイレクトすることを確認できる場合、真陽性が示されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="5ed75-161">**推奨されるアクション**: 応答 URL と、アプリによって要求されたスコープを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="5ed75-162">調査に基づいて、このアプリへのアクセスの禁止を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="5ed75-163">このアプリによって要求されたアクセス許可のレベルと、アクセスを許可したユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="5ed75-164">アプリへのアクセスを禁止するには、 [OAuth アプリ] ページで、禁止するアプリが表示されている行の禁止アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="5ed75-165">自分がインストールして承認したアプリが禁止されたことをユーザーに通知するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="5ed75-166">その通知により、ユーザーは、アプリが無効になり、接続されているアプリにアクセスできなくなることがわかります。</span><span class="sxs-lookup"><span data-stu-id="5ed75-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="5ed75-167">ユーザーに知らせたくない場合は、ダイアログの [この禁止されたアプリにアクセス許可を付与したユーザーに通知を送信します] の選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="5ed75-168">アプリが使用禁止になることをアプリのユーザーに知らせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ed75-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="5ed75-169">**B-TP**: 調査の後、アプリに組織での正当なビジネス上の用途があることを確認できた場合。</span><span class="sxs-lookup"><span data-stu-id="5ed75-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="5ed75-170">**推奨されるアクション**: アラートを無視します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="5ed75-171">攻撃対象を理解する</span><span class="sxs-lookup"><span data-stu-id="5ed75-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="5ed75-172">アプリによって実行されるすべてのアクティビティを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="5ed75-173">アプリが疑わしいと思われる場合は、別のアプリ ストアでそのアプリの名前と応答 URL を調査することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ed75-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="5ed75-174">アプリ ストアを確認するときは、次の種類のアプリに注目します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="5ed75-175">最近作成されたアプリ。</span><span class="sxs-lookup"><span data-stu-id="5ed75-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="5ed75-176">疑わしい応答 URL を持つアプリ。</span><span class="sxs-lookup"><span data-stu-id="5ed75-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="5ed75-177">最近更新されていないアプリ。</span><span class="sxs-lookup"><span data-stu-id="5ed75-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="5ed75-178">更新されていない場合、アプリがもうサポートされていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ed75-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="5ed75-179">アプリがまだ疑わしいと思われる場合は、そのアプリの名前、発行元の名前、および応答 URL をオンラインで調べることができます</span><span class="sxs-lookup"><span data-stu-id="5ed75-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="5ed75-180">永続性アラート</span><span class="sxs-lookup"><span data-stu-id="5ed75-180">Persistence alerts</span></span>

<span data-ttu-id="5ed75-181">このセクションでは、悪意のあるアクターが組織への足掛かりを維持しようとしている可能性があることを示すアラートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="5ed75-182">疑わしい OAuth スコープを含むアプリが受信トレイ ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="5ed75-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="5ed75-183">**重要度**: 中</span><span class="sxs-lookup"><span data-stu-id="5ed75-183">**Severity**: Medium</span></span>

<span data-ttu-id="5ed75-184">**MITRE ID**: T1137.005、T1114</span><span class="sxs-lookup"><span data-stu-id="5ed75-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="5ed75-185">この検出により、疑わしいスコープに同意し、疑わしい受信トレイ ルールを作成して、Graph API を介してユーザーのメール フォルダーおよびメッセージにアクセスした OAuth アプリが示されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="5ed75-186">すべてまたは特定のメールを別のメール アカウントに転送し、Graph がメールにアクセスして別のメール アカウントに送信するために呼び出すなどの受信トレイ ルールは、組織から情報を抽出する試みである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ed75-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="5ed75-187">**TP または FP?**</span><span class="sxs-lookup"><span data-stu-id="5ed75-187">**TP or FP?**</span></span>

- <span data-ttu-id="5ed75-188">**TP**: 受信トレイ ルールが OAuth のサードパーティ製のアプリによって作成され、疑わしいスコープが不明なソースから配信されていることを確認できる場合、真陽性が示されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="5ed75-189">**推奨されるアクション**: アプリを無効にして削除し、パスワードをリセットして、受信トレイ ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="5ed75-190">Azure Active Directory を使用してパスワードをリセットする方法に関するチュートリアルと、受信トレイ ルールを削除する方法に関するチュートリアルに従います。</span><span class="sxs-lookup"><span data-stu-id="5ed75-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="5ed75-191">**FP**: アプリが正当な理由で新規または個人の外部メール アカウントに受信トレイ ルールを作成したことを確認できる場合。</span><span class="sxs-lookup"><span data-stu-id="5ed75-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="5ed75-192">**推奨されるアクション**: アラートを無視します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="5ed75-193">攻撃対象を理解する</span><span class="sxs-lookup"><span data-stu-id="5ed75-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="5ed75-194">アプリによって実行されるすべてのアクティビティを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="5ed75-195">アプリによって付与されたスコープを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="5ed75-196">アプリによって作成された受信トレイ ルール アクションと条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="5ed75-197">コレクションのアラート</span><span class="sxs-lookup"><span data-stu-id="5ed75-197">Collection alerts</span></span>

<span data-ttu-id="5ed75-198">このセクションでは、悪意のあるアクターが目標に対して関心のあるデータを組織から収集しようとしている可能性があることを示すアラートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="5ed75-199">アプリがメールを読み取るための匿名の Graph 呼び出しを実行した</span><span class="sxs-lookup"><span data-stu-id="5ed75-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="5ed75-200">**重要度**: 中</span><span class="sxs-lookup"><span data-stu-id="5ed75-200">**Severity**: Medium</span></span>

<span data-ttu-id="5ed75-201">**MITRE ID**: T1114</span><span class="sxs-lookup"><span data-stu-id="5ed75-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="5ed75-202">この検出により、基幹業務 (LOB) OAuth アプリが、Graph API を通してユーザーの異常な、および大量のメール フォルダおよびメッセージにアクセスしたことが示されます。これは、組織のへの侵害が試行されたことを示す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ed75-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="5ed75-203">**TP または FP?**</span><span class="sxs-lookup"><span data-stu-id="5ed75-203">**TP or FP?**</span></span>

- <span data-ttu-id="5ed75-204">**TP**: Graph による異常なアクティビティが基幹業務 (LOB) OAuth アプリによって実行されたことを確認できる場合、真陽性が示されます。</span><span class="sxs-lookup"><span data-stu-id="5ed75-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="5ed75-205">**推奨されるアクション**: アプリを一時的に無効にし、パスワードをリセットしてからアプリを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="5ed75-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="5ed75-206">Azure Active Directory を使用してパスワードをリセットする方法に関するチュートリアルに従います。</span><span class="sxs-lookup"><span data-stu-id="5ed75-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="5ed75-207">**FP**: アプリが異常に多い量の Graph 呼び出しを行うよう意図されていることを確認できる場合。</span><span class="sxs-lookup"><span data-stu-id="5ed75-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="5ed75-208">**推奨されるアクション**: アラートを無視します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="5ed75-209">攻撃対象を理解する</span><span class="sxs-lookup"><span data-stu-id="5ed75-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="5ed75-210">メールを読み取り、ユーザーのメールに関する機密情報の収集を試行するための Graph のその他のアクティビティをさらに理解するには、このアプリによって実行されたイベントのアクティビティ ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="5ed75-211">予期しない資格情報がアプリに追加されないか監視します。</span><span class="sxs-lookup"><span data-stu-id="5ed75-211">Monitor for unexpected credential being added to the app.</span></span>
