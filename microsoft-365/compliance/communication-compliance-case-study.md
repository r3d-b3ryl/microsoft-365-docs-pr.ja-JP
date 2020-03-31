---
title: ケーススタディ-Contoso 社が Microsoft Teams および Exchange の通信に対して不快な言語ポリシーを迅速に構成する
description: Contoso 社のケーススタディと、Microsoft Teams および Exchange Online コミュニケーションで不快な言葉を監視するための通信コンプライアンスポリシーを迅速に構成する方法
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 4a119e0ec082893d393d1b43af76b41dc93c76a1
ms.sourcegitcommit: 144c0f3c2c6112bffc5a9b04392a38123a979ebc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053074"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-and-exchange-communications"></a><span data-ttu-id="5fd0c-103">ケーススタディ-Contoso 社が Microsoft Teams および Exchange の通信に対して不快な言語ポリシーを迅速に構成する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-103">Case study - Contoso quickly configures an offensive language policy for Microsoft Teams and Exchange communications</span></span>

<span data-ttu-id="5fd0c-104">Microsoft 365 の通信コンプライアンスは、組織内の不適切なメッセージに対する修復措置を検出、取得、および解決するのに役立つため、コミュニケーションリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-104">Communication compliance in Microsoft 365 helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="5fd0c-105">定義済みおよびカスタムのポリシーを使用すると、ポリシーの一致に関する内部通信と外部通信をスキャンして、指定したレビュー担当者がそれらを調査できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-105">Pre-defined and custom policies allow you to scan internal and external communications for policy matches so they can be examined by designated reviewers.</span></span> <span data-ttu-id="5fd0c-106">レビューアーは、組織内のスキャンされた電子メール、Microsoft Teams、またはサードパーティのコミュニケーションを調査し、適切な修復処置を行って、組織のメッセージ標準に準拠していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-106">Reviewers can investigate scanned email, Microsoft Teams, or third-party communications in your organization and take appropriate remediation actions to make sure they're compliant with your organization's message standards.</span></span>

<span data-ttu-id="5fd0c-107">Contoso Corporation は、不快感を与える言葉を監視するポリシーをすばやく構成する必要がある架空の組織です。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-107">The Contoso Corporation is a fictional organization that needs to quickly configure a policy to monitor for offensive language.</span></span> <span data-ttu-id="5fd0c-108">従業員に対しては主に Microsoft 365 を使用していますが、従業員には会社のポリシーを適用するための新しい要件があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-108">They have been using Microsoft 365 primarily for email and Microsoft Teams support for their employees but have new requirements to enforce company policy around workplace harassment.</span></span> <span data-ttu-id="5fd0c-109">Contoso 社の IT 管理者およびコンプライアンスの専門家は、Microsoft 365 の使用に関する基本事項について基本的な理解を深めており、コミュニケーションのコンプライアンスをすばやく始める方法についてのエンドツーエンドのガイダンスを求めています。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-109">Contoso IT administrators and compliance specialists have a basic understanding of the fundamentals of working with Microsoft 365 and are looking for end-to-end guidance for how to quickly get started with communication compliance.</span></span>

<span data-ttu-id="5fd0c-110">このケーススタディでは、有害な言語の通信を監視するための通信コンプライアンスポリシーをすばやく構成するための基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-110">This case study will cover the basics for quickly configuring a communication compliance policy to monitor communications for offensive language.</span></span> <span data-ttu-id="5fd0c-111">このガイダンスには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-111">This guidance includes:</span></span>

- <span data-ttu-id="5fd0c-112">手順 1-通信のコンプライアンスを計画する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-112">Step 1 - Planning for communication compliance</span></span>
- <span data-ttu-id="5fd0c-113">手順 2-Microsoft 365 での通信コンプライアンスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5fd0c-113">Step 2 - Accessing communication compliance in Microsoft 365</span></span>
- <span data-ttu-id="5fd0c-114">手順 3-前提条件を構成し、通信コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-114">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>
- <span data-ttu-id="5fd0c-115">ステップ 4-通知の調査と修復</span><span class="sxs-lookup"><span data-stu-id="5fd0c-115">Step 4 - Investigation and remediation of alerts</span></span>

## <a name="step-1---planning-for-communication-compliance"></a><span data-ttu-id="5fd0c-116">手順 1-通信のコンプライアンスを計画する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-116">Step 1 - Planning for communication compliance</span></span>

<span data-ttu-id="5fd0c-117">Contoso 社の IT 管理者およびコンプライアンスの専門家は、Microsoft 365 のコンプライアンスソリューションに関するオンラインウェビナーに参加しており、コミュニケーションコンプライアンスポリシーが、workplace 嫌がらせを削減するために更新された企業ポリシー要件を満たすのを支援することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-117">Contoso IT administrators and compliance specialists attended online webinars about compliance solutions in Microsoft 365 and decided that communication compliance policies will help them meet the updated corporate policy requirements for reducing workplace harassment.</span></span> <span data-ttu-id="5fd0c-118">共同作業では、Exchange Online で送信された電子メールメッセージ内の Microsoft Teams で送信されるチャットに対して、不快な言葉を監視する通信コンプライアンスポリシーを作成して有効にする計画が策定されました。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-118">Working together, they've developed a plan to create and enable a communication compliance policy that will monitor for offensive language for chats sent in Microsoft Teams in email messages sent in Exchange Online.</span></span> <span data-ttu-id="5fd0c-119">プランには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-119">Their plan includes identifying:</span></span>

- <span data-ttu-id="5fd0c-120">通信コンプライアンス機能にアクセスする必要がある IT 管理者。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-120">The IT administrators that need access to communication compliance features.</span></span>
- <span data-ttu-id="5fd0c-121">コミュニケーションポリシーを作成および管理する必要があるコンプライアンススペシャリスト。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-121">The compliance specialists that need to create and manage communication policies.</span></span>
- <span data-ttu-id="5fd0c-122">コミュニケーションのコンプライアンス警告を調査および修復する必要がある、他の部門 (人事、法律など) のコンプライアンススペシャリストおよびその他の仕事仲間。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-122">The compliance specialists and other colleague in other departments (Human Resources, Legal, etc.) that need to investigate and remediate communication compliance alerts.</span></span>
- <span data-ttu-id="5fd0c-123">通信コンプライアンス不快な言語ポリシーの範囲内となるユーザー。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-123">The users that will be in-scope for the communication compliance offensive language policy.</span></span>

### <a name="licensing"></a><span data-ttu-id="5fd0c-124">ライセンス</span><span class="sxs-lookup"><span data-stu-id="5fd0c-124">Licensing</span></span>

<span data-ttu-id="5fd0c-125">最初の手順は、Contoso 社の Microsoft 365 ライセンスに、コミュニケーションコンプライアンスソリューションのサポートが含まれていることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-125">The first step is to confirm that Contoso's Microsoft 365 licensing includes support for the communication compliance solution.</span></span> <span data-ttu-id="5fd0c-126">通信コンプライアンスにアクセスして使用するために、Contoso 社の IT 管理者は Contoso に次のいずれかの情報が含まれていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-126">To access and use communication compliance, Contoso IT administrators need to verify that Contoso has one of the following:</span></span>

- <span data-ttu-id="5fd0c-127">Microsoft 365 E5 サブスクリプション (有料または試用版)</span><span class="sxs-lookup"><span data-stu-id="5fd0c-127">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="5fd0c-128">Office 365 Enterprise E3 ライセンス (高度なコンプライアンス アドオン付き)</span><span class="sxs-lookup"><span data-stu-id="5fd0c-128">Office 365 Enterprise E3 license with the Advanced Compliance add-on</span></span>
- <span data-ttu-id="5fd0c-129">Office 365 Enterprise E5 サブスクリプション (有料または試用版)</span><span class="sxs-lookup"><span data-stu-id="5fd0c-129">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>

<span data-ttu-id="5fd0c-130">また、通信コンプライアンスポリシーに含まれているユーザーが上記のいずれかのライセンスに割り当てられていることを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-130">They must also confirm that users included in communication compliance policies must be assigned to one of the licenses listed above.</span></span>

<span data-ttu-id="5fd0c-131">Contoso 社の IT 管理者は、次の手順を実行して Contoso のライセンスサポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-131">Contoso IT administrators take the following steps to verify the licensing support for Contoso:</span></span>

1. <span data-ttu-id="5fd0c-132">IT 管理者は、 **microsoft 365 管理センター** [https://admin.microsoft.com)にサインインして](https://admin.microsoft.com)、 **microsoft 365 管理センター** > **請求** > **ライセンス**に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-132">IT administrators sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Billing** > **Licenses**.</span></span>

2. <span data-ttu-id="5fd0c-133">ここでは、通信コンプライアンスのサポートを含む[ライセンスオプション](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin)の1つを持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-133">Here they confirm that they have one of the [license options](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) that includes support for communication compliance.</span></span>

![コミュニケーションコンプライアンスライセンス](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a><span data-ttu-id="5fd0c-135">通信コンプライアンスのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5fd0c-135">Permissions for communication compliance</span></span>

<span data-ttu-id="5fd0c-136">既定では、全体管理者は通信コンプライアンス機能にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-136">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="5fd0c-137">Contoso IT 管理者とコンプライアンス担当者がコミュニケーションコンプライアンスにアクセスできるように、[アクセス許可を構成する必要があり](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance)ます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-137">[Permissions must be configured](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance) so that Contoso IT administrators and compliance specialists have access to communication compliance.</span></span>

1. <span data-ttu-id="5fd0c-138">Contoso IT 管理者は、 **office 365 の [セキュリティとコンプライアンスセンター**のアクセス許可] ページにサインインします[(https://protection.office.com/permissions) ](https://protection.office.com/permissions)グローバル管理者アカウントの資格情報を使用して、office 365 で役割を表示および管理するためのリンクを選択します)。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-138">Contoso IT administrators sign into the **Office 365 Security and Compliance center** permissions page [(https://protection.office.com/permissions)](https://protection.office.com/permissions) using credentials for a global administrator account and select the link to view and manage roles in Office 365.</span></span>
2. <span data-ttu-id="5fd0c-139">[**作成**] を選択すると、新しい役割グループに [*通信コンプライアンス*] のフレンドリ名が与えられ、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-139">After selecting **Create**, they give the new role group a friendly name of "*Communication compliance*" and select **Next**.</span></span>
3. <span data-ttu-id="5fd0c-140">[**役割の選択**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-140">They select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="5fd0c-141">必要な役割を追加するには、*監督レビュー管理者*、*ケース管理*、*コンプライアンス管理者*、*およびレビュー*のチェックボックスをオンにし、[**追加**]、[**完了]、** [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-141">They add the required roles by selecting the checkbox for *Supervisory Review Administrator*, *Case Management*, *Compliance Administrator*, and *Review*, then they select **Add**, **Done,** and **Next**.</span></span>

![コミュニケーションコンプライアンスの役割](../media/communication-compliance-case-roles.png)

4. <span data-ttu-id="5fd0c-143">次に、IT 管理者は [**メンバーの選択**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-143">Next, the IT administrators select **Choose members** then select **Add**.</span></span> <span data-ttu-id="5fd0c-144">ポリシーを作成するすべてのユーザーとグループのチェックボックスをオンにして、ポリシーの一致でメッセージを管理します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-144">The select the checkbox for all the users and groups that they want to create policies and manage messages with policy matches.</span></span> <span data-ttu-id="5fd0c-145">最初の計画で特定された人事および法務部門に IT 管理者、コンプライアンスの専門家、その他の仕事仲間を追加し、[**追加**]、[**完了**]、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-145">They add the IT administrators, compliance specialists, and other colleagues in Human Resources and Legal departments that they identified in the initial planning, then select **Add**, **Done**, and **Next**.</span></span>
5. <span data-ttu-id="5fd0c-146">アクセス許可を確定するには、IT 管理者が [**役割グループの作成**] を選択して終了します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-146">To finalize the permissions, the IT administrators select **Create role group** to finish.</span></span> <span data-ttu-id="5fd0c-147">Contoso 社の Microsoft 365 サービスでは、役割が有効になるまでに約30分かかります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-147">It will take about 30 minutes for the roles to be effective in Contoso's Microsoft 365 service.</span></span>

![コミュニケーションコンプライアンスレビュー](../media/communication-compliance-case-review.png)

## <a name="step-2---accessing-communication-compliance-in-microsoft-365"></a><span data-ttu-id="5fd0c-149">手順 2-Microsoft 365 での通信コンプライアンスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5fd0c-149">Step 2 - Accessing communication compliance in Microsoft 365</span></span>

<span data-ttu-id="5fd0c-150">通信コンプライアンスのアクセス許可を構成した後、新しい役割グループで定義されている Contoso IT 管理者とコンプライアンススペシャリストは、Microsoft 365 の通信コンプライアンスソリューションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-150">After configuring the permissions for communication compliance, Contoso IT administrators and compliance specialists defined in the new role group can access the communication compliance solution in Microsoft 365.</span></span> <span data-ttu-id="5fd0c-151">Contoso 社の IT 管理者およびコンプライアンスの専門家は、コミュニケーションへのコンプライアンスにアクセスし、新しいポリシーの作成を開始するためのいくつかの方法を備えています。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-151">Contoso IT administrators and compliance specialists have several ways to access communication compliance and get started creating a new policy:</span></span>

- <span data-ttu-id="5fd0c-152">コミュニケーションコンプライアンスソリューションから直接開始する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-152">Starting directly from the communication compliance solution</span></span>
- <span data-ttu-id="5fd0c-153">Microsoft 365 コンプライアンスセンターからの開始</span><span class="sxs-lookup"><span data-stu-id="5fd0c-153">Starting from the Microsoft 365 compliance center</span></span>
- <span data-ttu-id="5fd0c-154">Microsoft 365 ソリューションカタログからの開始</span><span class="sxs-lookup"><span data-stu-id="5fd0c-154">Starting from the Microsoft 365 solution catalog</span></span>
- <span data-ttu-id="5fd0c-155">Microsoft 365 管理センターから開始する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-155">Starting from the Microsoft 365 admin center</span></span>

### <a name="starting-directly-from-the-communication-compliance-solution"></a><span data-ttu-id="5fd0c-156">コミュニケーションコンプライアンスソリューションから直接開始する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-156">Starting directly from the communication compliance solution</span></span>

<span data-ttu-id="5fd0c-157">ソリューションにアクセスする最も簡単な方法は、**コミュニケーションコンプライアンス**(<https://compliance.microsoft.com/supervisoryreview>) ソリューションに直接サインインすることです。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-157">The quickest way to access the solution is to sign in directly to the **Communication compliance** (<https://compliance.microsoft.com/supervisoryreview>) solution.</span></span> <span data-ttu-id="5fd0c-158">このリンクを使用すると、Contoso IT 管理者とコンプライアンスの専門家は、通知の状態をすばやく確認し、定義済みのテンプレートから新しいポリシーを作成できる、コミュニケーションコンプライアンスの概要ダッシュボードに送られます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-158">Using this link, Contoso IT administrators and compliance specialists will be directed to the communication compliance Overview dashboard where you can quickly review the status of alerts and create new policies from the pre-defined templates.</span></span>

![コミュニケーションコンプライアンスの概要](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a><span data-ttu-id="5fd0c-160">Microsoft 365 コンプライアンスセンターからの開始</span><span class="sxs-lookup"><span data-stu-id="5fd0c-160">Starting from the Microsoft 365 compliance center</span></span>

<span data-ttu-id="5fd0c-161">Contoso IT 管理者とコンプライアンス担当者がコミュニケーションコンプライアンスソリューションにアクセスするもう1つの簡単な方法は、 **Microsoft 365 コンプライアンスセンター** [(https://compliance.microsoft.com)](https://compliance.microsoft.com)) に直接サインインすることです。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-161">Another easy way for Contoso IT administrators and compliance specialists to access the communication compliance solution is to sign in directly to the **Microsoft 365 compliance center** [(https://compliance.microsoft.com)](https://compliance.microsoft.com).</span></span> <span data-ttu-id="5fd0c-162">サインインした後、ユーザーは、すべてのコンプライアンスソリューションを表示するために [**すべて表示**] を選択するだけで、開始する**通信コンプライアンス**ソリューションを選択するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-162">After signing in, users simply need to select the **Show all** control to display all the compliance solutions and then select the **Communication compliance** solution to get started.</span></span>

![コンプライアンスセンター](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a><span data-ttu-id="5fd0c-164">Microsoft 365 ソリューションカタログからの開始</span><span class="sxs-lookup"><span data-stu-id="5fd0c-164">Starting from the Microsoft 365 solution catalog</span></span>

<span data-ttu-id="5fd0c-165">Contoso 社の IT 管理者およびコンプライアンス担当者は、Microsoft 365 ソリューションカタログを選択して、コミュニケーションコンプライアンスソリューションにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-165">Contoso IT administrators and compliance specialists could also choose to access the communication compliance solution by selecting the Microsoft 365 solution catalog.</span></span> <span data-ttu-id="5fd0c-166">**Microsoft 365 コンプライアンスセンター**で、左側のナビゲーションの [**ソリューション**の**カタログ**] セクションを選択すると、すべての microsoft 365 コンプライアンスソリューションを一覧表示したソリューションカタログを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-166">By selecting **Catalog** in **Solutions** section of the left navigation while in the **Microsoft 365 compliance center**, they can open the solution catalog listing all Microsoft 365 compliance solutions.</span></span> <span data-ttu-id="5fd0c-167">「 **Insider リスク管理**」セクションまでスクロールすると、Contoso IT 管理者は通信のコンプライアンスを選択して開始することができます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-167">Scrolling down to the **Insider risk management** section, Contoso IT administrators can select Communication compliance to get started.</span></span> <span data-ttu-id="5fd0c-168">Contoso 社の IT 管理者は、[ナビゲーションに表示] コントロールを使用して、コミュニケーションコンプライアンスソリューションを左側のナビゲーションウィンドウにピン留めし、今後のサインイン時にすばやくアクセスできるようにすることも決定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-168">Contoso IT administrators also decide to use the Show in navigation control to pin the communication compliance solution to the left-navigation pane for quicker access when they sign in going forward.</span></span>

![ソリューションカタログ](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a><span data-ttu-id="5fd0c-170">Microsoft 365 管理センターから開始する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-170">Starting from the Microsoft 365 admin center</span></span>

<span data-ttu-id="5fd0c-171">Microsoft 365 管理センターから開始して通信コンプライアンスにアクセスするには、Contoso IT 管理者とコンプライアンス担当者が microsoft 365[管理https://admin.microsoft.com)センターに](https://admin.microsoft.com)サインインし、 **microsoft 365 管理センター** > **コンプライアンス**に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-171">To access communication compliance when starting from the Microsoft 365 admin center, Contoso IT administrators and compliance specialists sign in to the Microsoft 365 admin center [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Compliance**.</span></span>

![通信コンプライアンスリンク](../media/communication-compliance-case-compliance-link.png)

<span data-ttu-id="5fd0c-173">これにより、 **Office 365 セキュリティ/コンプライアンスセンター**が開き、ページ上部のバナーで提供される**Microsoft 365 コンプライアンスセンター**へのリンクを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-173">This opens the **Office 365 Security and Compliance center**, and they must select the link to the **Microsoft 365 compliance center** provided in the banner at the top of the page.</span></span>

![Office 365 セキュリティ/コンプライアンスセンター](../media/communication-compliance-case-scc.png)

<span data-ttu-id="5fd0c-175">**Microsoft 365 コンプライアンスセンター**では、Contoso IT 管理者は [**すべて表示**] を選択して、コンプライアンスソリューションの完全な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-175">Once in the **Microsoft 365 compliance center**, Contoso IT administrators select **Show all** to display the full list of compliance solutions.</span></span>

![通信コンプライアンスメニュー](../media/communication-compliance-case-show-all.png)

<span data-ttu-id="5fd0c-177">[**すべて表示**] を選択すると、Contoso IT 管理者はコミュニケーションコンプライアンスソリューションにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-177">After selecting **Show all**, the Contoso IT administrators can access the communication compliance solution.</span></span>

![コミュニケーションコンプライアンスの概要](../media/communication-compliance-case-overview.png)

## <a name="step-3---configuring-prerequisites-and-creating-a-communication-compliance-policy"></a><span data-ttu-id="5fd0c-179">手順 3-前提条件を構成し、通信コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-179">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>

<span data-ttu-id="5fd0c-180">通信コンプライアンスポリシーの使用を開始するには、攻撃的な言葉を監視するように新しいポリシーを設定する前に Contoso IT 管理者が構成する必要があるいくつかの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-180">To get started with a communication compliance policy, there are several prerequisites that Contoso IT administrators need to configure before setting up the new policy to monitor for offensive language.</span></span> <span data-ttu-id="5fd0c-181">これらの前提条件が満たされたら、Contoso IT 管理者とコンプライアンス担当者が新しいポリシーを構成し、コンプライアンススペシャリストが調査を開始し、生成されたすべての警告を修復することができます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-181">After these prerequisites have been completed, Contoso IT administrators and compliance specialists can configure the new policy and compliance specialists can start investigation and remediating any generated alerts.</span></span>

### <a name="enabling-auditing-in-office-365"></a><span data-ttu-id="5fd0c-182">Office 365 で監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="5fd0c-182">Enabling auditing in Office 365</span></span>

<span data-ttu-id="5fd0c-183">通信のコンプライアンスでは、監査ログを使用して通知を表示し、レビュー担当者が行った修復アクションを追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-183">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="5fd0c-184">監査ログは、定義された組織のポリシーに関連付けられているすべてのアクティビティの要約です。または、通信コンプライアンスポリシーに変更がある場合はいつでも、その概要です。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-184">The audit logs are a summary of all activities associated with a defined organizational policy or anytime there is a change to a communication compliance policy.</span></span>

<span data-ttu-id="5fd0c-185">Contoso 社の IT 管理者は、監査を有効[にするため](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)の手順を確認して完了します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-185">Contoso IT administrators review and complete the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) to turn on auditing.</span></span> <span data-ttu-id="5fd0c-186">監査を有効にすると、監査ログが準備されていて、準備が完了してから数時間で検索を実行できることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-186">After they turn on auditing, a message is displayed that says the audit log is being prepared and that they can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="5fd0c-187">Contoso 社の IT 管理者は、このアクションを1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-187">The Contoso IT administrators only have to do this action once.</span></span>

### <a name="setting-up-a-group-for-in-scope-users"></a><span data-ttu-id="5fd0c-188">スコープ内ユーザーのグループの設定</span><span class="sxs-lookup"><span data-stu-id="5fd0c-188">Setting up a group for in-scope users</span></span>

<span data-ttu-id="5fd0c-189">Contoso 社のコンプライアンス担当者が、不快な言葉を監視するコミュニケーションポリシーに従業員を追加することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-189">Contoso compliance specialists want to add all employee to the communication policy that will monitor for offensive language.</span></span> <span data-ttu-id="5fd0c-190">各従業員のユーザーアカウントをポリシーに個別に追加することを決定することもできますが、これはより簡単になり、このポリシーのユーザーに対して**すべての従業員**配布グループを使用するための時間が大幅に節約されることが決定されました。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-190">They could decide to add each employee user account to the policy separately, but they've decided it is much easier and saves a lot of time to use an **All Employees** distribution group for the users for this policy.</span></span>

<span data-ttu-id="5fd0c-191">Contoso 社の従業員全員を含む新しいグループを作成する必要があるので、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-191">They need to create a new group to include all Contoso employees, so they take the following steps:</span></span>

1. <span data-ttu-id="5fd0c-192">Contoso it 管理者は、 **microsoft 365 管理センター** [https://admin.microsoft.com)にサインインして](https://admin.microsoft.com)、 **microsoft 365 管理センター** > **グループ** > **グループ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-192">Contoso IT administrators IT sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Groups** > **Groups**.</span></span>
2. <span data-ttu-id="5fd0c-193">[**グループの追加**] を選択し、ウィザードを完了して、新しい*Office 365 グループ*または*配布グループ*を作成します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-193">They select **Add a group** and complete the wizard to create a new *Office 365 group* or *Distribution group*.</span></span>

![グループ](../media/communication-compliance-case-all-employees.png)

3. <span data-ttu-id="5fd0c-195">新しいグループを作成した後、すべての Contoso ユーザーを新しいグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-195">After the new group is created, they need to add all Contoso users to the new group.</span></span> <span data-ttu-id="5fd0c-196">**Exchange 管理センター** [https://outlook.office365.com/ecp) ](https://outlook.office365.com/ecp)を開き、 **exchange 管理センター** > の [**受信者** > **グループ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-196">They open the **Exchange admin center** [(https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) and navigate to **Exchange admin center** > **recipients** > **groups**.</span></span> <span data-ttu-id="5fd0c-197">Contoso IT 管理者は、メンバーシップ領域および作成した新しい*すべての従業員*グループを選択し、[**編集**] コントロールを選択して、すべての contoso 従業員をウィザードの新しいグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-197">The Contoso IT administrators select the Membership area and the new *All Employees* group they created and select the **Edit** control to add all Contoso employees to the new group in the wizard.</span></span>

![Exchange 管理センター](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a><span data-ttu-id="5fd0c-199">不快な言葉を監視するポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-199">Creating the policy to monitor for offensive language</span></span>

<span data-ttu-id="5fd0c-200">すべての前提条件が満たされたら、Contoso の IT 管理者とコンプライアンスの専門家が、不快な言葉を監視するための通信コンプライアンスポリシーを構成する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-200">With all the prerequisites completed, the IT administrators and the compliance specialists for Contoso are ready to configure the communication compliance policy to monitor for offensive language.</span></span> <span data-ttu-id="5fd0c-201">新しい不快な言語のポリシーテンプレートを使用すると、このポリシーの構成は簡単で短時間になります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-201">Using the new offensive language policy template, configuring this policy is simple and quick.</span></span>

1. <span data-ttu-id="5fd0c-202">Contoso IT 管理者およびコンプライアンスの専門家は、 **Microsoft 365 コンプライアンスセンター**にサインインし、左側のナビゲーションウィンドウから [**通信コンプライアンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-202">The Contoso IT administrators and compliance specialists sign into the **Microsoft 365 compliance center** and select **Communication compliance** from the left navigation pane.</span></span> <span data-ttu-id="5fd0c-203">この操作により、コミュニケーションコンプライアンスポリシーテンプレートのクイックリンクがある**概要**ダッシュボードが開きます。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-203">This action opens the **Overview** dashboard that has quick links for communication compliance policy templates.</span></span> <span data-ttu-id="5fd0c-204">[テンプレートの**開始**] を選択して、**不快感を得る言語テンプレートのモニター**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-204">They choose the **Monitor for offensive language** template by selecting **Get started** for the template.</span></span>

![コミュニケーションコンプライアンス不快な言語テンプレート](../media/communication-compliance-case-template.png)

2. <span data-ttu-id="5fd0c-206">ポリシーテンプレートウィザードでは、Contoso IT 管理者とコンプライアンスの専門家が連携して、**ポリシー名**、**監督対象のユーザーまたはグループ**、および**レビュー担当者**という3つの必須フィールドを完了します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-206">On the policy template wizard, the Contoso IT administrators and compliance specialists work together to complete the three required fields: **Policy name**, **Users or groups to supervise**, and **Reviewers**.</span></span>
3. <span data-ttu-id="5fd0c-207">ポリシーウィザードによって既にポリシーの名前が提案されているため、IT 管理者およびコンプライアンスの専門家は、提案された名前を保持し、残りのフィールドに焦点を当てることに決定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-207">Since the policy wizard has already suggested a name for the policy, the IT administrators and compliance specialists decide to keep the suggested name and focus on the remaining fields.</span></span> <span data-ttu-id="5fd0c-208">**ユーザーまたはグループ**の [監督] フィールドに [ *All employees* ] グループを選択し、[**レビュー担当者**] フィールドのポリシー通知を調査および修復する必要があるコンプライアンススペシャリストを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-208">They select the *All employees* group for the **Users or groups to supervise** field and select the compliance specialists that should investigate and remediate policy alerts for the **Reviewers** field.</span></span> <span data-ttu-id="5fd0c-209">ポリシーを構成して通知情報の収集を開始するための最後の手順として、[**ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-209">The last step to configure the policy and start gathering alert information is to select **Create policy**.</span></span>

![通信コンプライアンス不快な言語ウィザード](../media/communication-compliance-case-wizard.png)

## <a name="step-4--investigate-and-remediate-alerts"></a><span data-ttu-id="5fd0c-211">手順 4: 通知を調べて修復する</span><span class="sxs-lookup"><span data-stu-id="5fd0c-211">Step 4 – Investigate and remediate alerts</span></span>

<span data-ttu-id="5fd0c-212">これで、不快感を与える言語を監視するための通信コンプライアンスポリシーが構成されました。次の手順では、Contoso コンプライアンスの専門家がポリシーによって生成された警告を調査して修復します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-212">Now that the communication compliance policy to monitor for offensive language is configured, the next step for the Contoso compliance specialists will be to investigate and remediate any alerts generated by the policy.</span></span> <span data-ttu-id="5fd0c-213">ポリシーがすべての通信ソースチャネル内の通信を完全に処理し、通知が**通知ダッシュボード**に表示されるまでに最大24時間かかります。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-213">It will take up to 24 hours for the policy to fully process communications in all the communication source channels and for alerts to show up in the **Alert dashboard**.</span></span>

<span data-ttu-id="5fd0c-214">通知が生成された後、Contoso 社のコンプライアンス担当者は[ワークフローの指示](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate)に従って、不快な言葉の問題を調査および修復します。</span><span class="sxs-lookup"><span data-stu-id="5fd0c-214">After alerts are generated, Contoso compliance specialists will follow the [workflow instructions](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) to investigate and remediate offensive language issues.</span></span>
