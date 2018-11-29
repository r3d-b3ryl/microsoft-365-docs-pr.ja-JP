---
title: Contoso 社の IT インフラストラクチャおよびビジネス ニーズ
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のオンプレミスの IT インフラストラクチャの基本的な構造について、およびそのビジネス ニーズが Microsoft 365 Enterprise によってどのように満たされるかについて説明します。
ms.openlocfilehash: b507d1a44edc0b31b2ac5a3f949ecd8a72913311
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869110"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="6bd07-103">Contoso 社の IT インフラストラクチャおよびビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="6bd07-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="6bd07-104">**概要:** Contoso 社のオンプレミスの IT インフラストラクチャの基本的な構造について、およびそのビジネス ニーズが Microsoft 365 Enterprise によってどのように満たされるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>


<span data-ttu-id="6bd07-105">Contoso 社は、集中管理されたオンプレミスの IT インフラストラクチャから、クラウド包括型の IT インフラストラクチャへと移行しています。後者には、クラウドベースの個人生産性のワークロードとアプリケーションが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="6bd07-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="6bd07-106">Contoso 社の既存の IT インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="6bd07-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="6bd07-107">Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="6bd07-108">図 1 は、本社とアプリケーション データセンター、境界ネットワーク、およびインターネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="6bd07-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="6bd07-109">**図 1: Contoso 社の既存の IT インフラストラクチャ**</span><span class="sxs-lookup"><span data-stu-id="6bd07-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="6bd07-110">オンプレミス アプリケーション データセンターのホストは次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="6bd07-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="6bd07-111">SQL Server や他の Linux データベースを使用するカスタムの基幹業務アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="6bd07-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="6bd07-112">従来の SharePoint サーバーのセット。</span><span class="sxs-lookup"><span data-stu-id="6bd07-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="6bd07-113">ファイル記憶域用の組織およびチームレベルのサーバー。</span><span class="sxs-lookup"><span data-stu-id="6bd07-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="6bd07-p101">さらには、同様のアプリケーション セットを持つサーバー セットをサポートする各地域ハブ オフィスです。これらのサーバーは地域の IT 部門の管理下にあります。</span><span class="sxs-lookup"><span data-stu-id="6bd07-p101">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="6bd07-116">こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。</span><span class="sxs-lookup"><span data-stu-id="6bd07-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="6bd07-117">Contoso 社の本社の境界ネットワークでは、サーバーのさまざまなセットが次のことを実現します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="6bd07-118">パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの VPN ベースのリモート アクセス。</span><span class="sxs-lookup"><span data-stu-id="6bd07-118">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>
- <span data-ttu-id="6bd07-119">顧客が製品、部品、備品、またはサービスを発注できる Contoso 社のパブリック Web サイトのホスティング。</span><span class="sxs-lookup"><span data-stu-id="6bd07-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="6bd07-120">パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。</span><span class="sxs-lookup"><span data-stu-id="6bd07-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="6bd07-121">Contoso 社のビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="6bd07-121">Contoso's business needs</span></span>

<span data-ttu-id="6bd07-122">Contoso 社のビジネス ニーズは、5 つの主なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="6bd07-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="6bd07-123">生産性:</span><span class="sxs-lookup"><span data-stu-id="6bd07-123">Productivity:</span></span>

- <span data-ttu-id="6bd07-124">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="6bd07-124">Make collaboration easier</span></span>

  <span data-ttu-id="6bd07-125">メールとファイル共有ベースのグループ作業を、オンライン モデルに置き換えることで、文書のリアルタイム変更、簡単なオンライン会議、会話スレッドのキャプチャを可能にします。</span><span class="sxs-lookup"><span data-stu-id="6bd07-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="6bd07-126">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6bd07-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="6bd07-127">多くの従業員が自宅や現場で働いているため、ボトルネックとなっている VPN ソリューションを、クラウド内の Contoso 社のデータとリソースへの効率的なアクセスに変更します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="6bd07-128">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6bd07-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="6bd07-129">手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。</span><span class="sxs-lookup"><span data-stu-id="6bd07-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="6bd07-130">セキュリティ:</span><span class="sxs-lookup"><span data-stu-id="6bd07-130">Security:</span></span>

- <span data-ttu-id="6bd07-131">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="6bd07-131">Identity and access management</span></span>

  <span data-ttu-id="6bd07-132">多要素認証および他の形式の認証を適用し、ユーザーおよび管理者アカウントの資格情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="6bd07-133">脅威保護</span><span class="sxs-lookup"><span data-stu-id="6bd07-133">Threat protection</span></span>

  <span data-ttu-id="6bd07-134">メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="6bd07-135">情報保護</span><span class="sxs-lookup"><span data-stu-id="6bd07-135">Information protection</span></span>

  <span data-ttu-id="6bd07-136">顧客データ、設計仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-136">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="6bd07-137">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="6bd07-137">Security management</span></span>

  <span data-ttu-id="6bd07-138">セキュリティの状態を監視し、リアルタイムで脅威を検出して対応できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6bd07-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="6bd07-139">リモート/モバイル アクセスおよびビジネス パートナー:</span><span class="sxs-lookup"><span data-stu-id="6bd07-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="6bd07-140">リモート ワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="6bd07-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="6bd07-141">持ち込みデバイス (BYOD) と会社所有のデバイスの管理に着手し、確実にアクセスをセキュリティで保護し、アプリケーションを正しく動作させ、企業データを保護できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6bd07-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="6bd07-142">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="6bd07-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="6bd07-143">よくアクセスされているリソースをクラウドに移動することで、保守作業とサポートのコストを削減し、リモート アクセス ソリューションのパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="6bd07-143">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="6bd07-144">企業間 (B2B) のトランザクションにおける接続性を向上し、オーバーヘッドを削減する</span><span class="sxs-lookup"><span data-stu-id="6bd07-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="6bd07-145">老朽化が進み、維持にコストがかかるパートナー エクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6bd07-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="6bd07-146">コンプライアンス:</span><span class="sxs-lookup"><span data-stu-id="6bd07-146">Compliance:</span></span>

- <span data-ttu-id="6bd07-147">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="6bd07-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="6bd07-148">欧州連合の一般データ保護規則 (GDPR) などのデータ ストレージ、暗号化、データ プライバシー、個人データの規制に関する産業および地域の規則に準拠し、これを維持します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="6bd07-149">管理:</span><span class="sxs-lookup"><span data-stu-id="6bd07-149">Management:</span></span>

- <span data-ttu-id="6bd07-150">クライアント PC とデバイスで実行されているソフトウェアを管理するために、IT オーバーヘッドを削減します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="6bd07-151">組織全体で Windows オペレーティング システムと Microsoft Office の更新プログラムのインストールを自動化します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-151">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="6bd07-152">Contoso 社のビジネス ニーズを Microsoft 365 Enterprise にマッピングする</span><span class="sxs-lookup"><span data-stu-id="6bd07-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6bd07-153">Contoso 社の IT 部門は、展開に先立って次のビジネス ニーズを Microsoft 365 Enterprise E5 の機能にマッピングすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="6bd07-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="6bd07-154">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="6bd07-154">**Category**</span></span> | <span data-ttu-id="6bd07-155">**ビジネス ニーズ**</span><span class="sxs-lookup"><span data-stu-id="6bd07-155">**Business need**</span></span> | <span data-ttu-id="6bd07-156">**Microsoft 365 Enterprise の製品または機能**</span><span class="sxs-lookup"><span data-stu-id="6bd07-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="6bd07-157">生産性</span><span class="sxs-lookup"><span data-stu-id="6bd07-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="6bd07-158">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="6bd07-158">Make collaboration easier</span></span> | <span data-ttu-id="6bd07-159">Teams、SharePoint Online、Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bd07-159">Teams, SharePoint Online, Skype for Business Online</span></span> |
|  | <span data-ttu-id="6bd07-160">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6bd07-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="6bd07-161">Office 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="6bd07-161">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6bd07-162">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6bd07-162">Increase creativity and innovation</span></span> | <span data-ttu-id="6bd07-163">Windows Ink、職場の Cortana、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6bd07-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="6bd07-164">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6bd07-164">Security</span></span> |  |  |
|  | <span data-ttu-id="6bd07-165">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="6bd07-165">Identity & access management</span></span> | <span data-ttu-id="6bd07-166">多要素認証 (MFA) および Azure AD Privileged Identity Management (PIM) 付きの専用のグローバル管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="6bd07-166">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="6bd07-167">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="6bd07-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="6bd07-168">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="6bd07-168">Conditional access</span></span> <BR> <span data-ttu-id="6bd07-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="6bd07-169">Windows Hello</span></span> <BR> <span data-ttu-id="6bd07-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="6bd07-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="6bd07-171">脅威保護</span><span class="sxs-lookup"><span data-stu-id="6bd07-171">Threat protection</span></span> | <span data-ttu-id="6bd07-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="6bd07-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="6bd07-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="6bd07-173">Windows Defender</span></span> <BR> <span data-ttu-id="6bd07-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6bd07-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="6bd07-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6bd07-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="6bd07-176">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="6bd07-176">Office 365 Threat Intelligence</span></span> <BR> |
|  | <span data-ttu-id="6bd07-177">情報保護</span><span class="sxs-lookup"><span data-stu-id="6bd07-177">Information protection</span></span> | <span data-ttu-id="6bd07-178">Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="6bd07-178">Azure Information Protection (AIP)</span></span> <BR> <span data-ttu-id="6bd07-179">Office 365 データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="6bd07-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="6bd07-180">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="6bd07-180">Windows Information Protection</span></span> <BR> <span data-ttu-id="6bd07-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6bd07-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="6bd07-182">Office 365 Cloud App Security (CAS)</span><span class="sxs-lookup"><span data-stu-id="6bd07-182">Office 365 Cloud App Security (CAS)</span></span> <BR> <span data-ttu-id="6bd07-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6bd07-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6bd07-184">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="6bd07-184">Security management</span></span> | <span data-ttu-id="6bd07-185">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="6bd07-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="6bd07-186">Windows Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="6bd07-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="6bd07-187">リモート/モバイル アクセスおよびビジネス パートナー</span><span class="sxs-lookup"><span data-stu-id="6bd07-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="6bd07-188">リモート ワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="6bd07-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="6bd07-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6bd07-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6bd07-190">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="6bd07-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="6bd07-191">Office 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="6bd07-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6bd07-192">B2B のトランザクションにおける接続性を向上し、オーバーヘッドを削減する</span><span class="sxs-lookup"><span data-stu-id="6bd07-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="6bd07-193">フェデレーション認証とクラウドベースのリソース</span><span class="sxs-lookup"><span data-stu-id="6bd07-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="6bd07-194">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="6bd07-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="6bd07-195">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="6bd07-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="6bd07-196">Office 365 の GDPR 機能</span><span class="sxs-lookup"><span data-stu-id="6bd07-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="6bd07-197">管理</span><span class="sxs-lookup"><span data-stu-id="6bd07-197">Management</span></span> |  |  |
|  | <span data-ttu-id="6bd07-198">クライアントの更新プログラムをインストールするため、IT オーバーヘッドを削減する</span><span class="sxs-lookup"><span data-stu-id="6bd07-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="6bd07-199">展開リング</span><span class="sxs-lookup"><span data-stu-id="6bd07-199">Deployment rings</span></span> <BR> <span data-ttu-id="6bd07-200">適切な Windows 10 のアップグレードと Autopilot</span><span class="sxs-lookup"><span data-stu-id="6bd07-200">Windows 10 upgrade in place and Autopilot</span></span> <BR> <span data-ttu-id="6bd07-201">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="6bd07-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="6bd07-202">次の手順</span><span class="sxs-lookup"><span data-stu-id="6bd07-202">Next step</span></span>

<span data-ttu-id="6bd07-203">Contoso 社のオンプレミス ネットワークと、組織全体の Microsoft 365 のクラウドベースのリソースへのアクセスと待ち時間を最適化した方法について[確認](contoso-networking.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bd07-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bd07-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bd07-204">See also</span></span>

[<span data-ttu-id="6bd07-205">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="6bd07-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6bd07-206">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="6bd07-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
