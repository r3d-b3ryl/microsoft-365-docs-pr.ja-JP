---
title: Contoso 社の IT インフラストラクチャおよびビジネス ニーズ
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のオンプレミスの IT インフラストラクチャの基本的な構造について、およびそのビジネス ニーズが Microsoft 365 Enterprise によってどのように満たされたかについて説明します。
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369588"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="6282f-103">Contoso 社の IT インフラストラクチャおよびビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="6282f-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="6282f-104">**概要:** Contoso 社のオンプレミスの IT インフラストラクチャの基本的な構造について、およびそのビジネス ニーズが Microsoft 365 Enterprise によってどのように満たされたかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6282f-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="6282f-105">Contoso 社は、集中管理されたオンプレミスの IT インフラストラクチャから、クラウド包括型の IT インフラストラクチャへと移行しています。後者には、クラウドベースの個人生産性のワークロードとアプリケーションが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="6282f-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="6282f-106">Contoso 社の既存の IT インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="6282f-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="6282f-107">Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。</span><span class="sxs-lookup"><span data-stu-id="6282f-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="6282f-108">図 1 は、本社とアプリケーション データセンター、境界ネットワーク、およびインターネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="6282f-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contoso 社の既存の IT インフラストラクチャ](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="6282f-110">**図 1: Contoso 社の既存の IT インフラストラクチャ**</span><span class="sxs-lookup"><span data-stu-id="6282f-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="6282f-111">オンプレミス アプリケーション データセンターのホストは次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="6282f-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="6282f-112">SQL Server や他の Linux データベースを使用するカスタムの基幹業務アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="6282f-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="6282f-113">従来の SharePoint サーバーのセット。</span><span class="sxs-lookup"><span data-stu-id="6282f-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="6282f-114">ファイル記憶域用の組織およびチームレベルのサーバー。</span><span class="sxs-lookup"><span data-stu-id="6282f-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="6282f-115">さらに、各地域のハブ オフィスは、同様のアプリケーション セットを持つサーバー セットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6282f-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="6282f-116">これらのサーバーは、地域の IT 部門が管理します。</span><span class="sxs-lookup"><span data-stu-id="6282f-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="6282f-117">こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。</span><span class="sxs-lookup"><span data-stu-id="6282f-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="6282f-118">Contoso 社の本社の境界ネットワークでは、サーバーのさまざまなセットが次のことを実現します。</span><span class="sxs-lookup"><span data-stu-id="6282f-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="6282f-119">顧客が製品、部品、備品、またはサービスを発注できる Contoso 社のパブリック Web サイトのホスティング。</span><span class="sxs-lookup"><span data-stu-id="6282f-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="6282f-120">パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。</span><span class="sxs-lookup"><span data-stu-id="6282f-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="6282f-121">パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの仮想プライベート ネットワーク (VPN) ベースのリモート アクセス。</span><span class="sxs-lookup"><span data-stu-id="6282f-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="6282f-122">Contoso 社のビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="6282f-122">Contoso's business needs</span></span>

<span data-ttu-id="6282f-123">Contoso 社のビジネス ニーズは、5 つの主なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="6282f-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="6282f-124">生産性:</span><span class="sxs-lookup"><span data-stu-id="6282f-124">Productivity:</span></span>

- <span data-ttu-id="6282f-125">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="6282f-125">Make collaboration easier</span></span>

  <span data-ttu-id="6282f-126">メールとファイル共有ベースのグループ作業を、オンライン モデルに置き換えることで、文書のリアルタイム変更、簡単なオンライン会議、会話スレッドのキャプチャを可能にします。</span><span class="sxs-lookup"><span data-stu-id="6282f-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="6282f-127">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6282f-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="6282f-128">多くの従業員が自宅や現場で働いているため、ボトルネックとなっている VPN ソリューションを、クラウド内の Contoso 社のデータとリソースへの効率的なアクセスに変更します。</span><span class="sxs-lookup"><span data-stu-id="6282f-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="6282f-129">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6282f-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="6282f-130">手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。</span><span class="sxs-lookup"><span data-stu-id="6282f-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="6282f-131">セキュリティ:</span><span class="sxs-lookup"><span data-stu-id="6282f-131">Security:</span></span>

- <span data-ttu-id="6282f-132">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="6282f-132">Identity and access management</span></span>

  <span data-ttu-id="6282f-133">多要素認証および他の形式の認証を適用し、ユーザーおよび管理者アカウントの資格情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="6282f-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="6282f-134">脅威保護</span><span class="sxs-lookup"><span data-stu-id="6282f-134">Threat protection</span></span>

  <span data-ttu-id="6282f-135">メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="6282f-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="6282f-136">情報保護</span><span class="sxs-lookup"><span data-stu-id="6282f-136">Information protection</span></span>

  <span data-ttu-id="6282f-137">顧客データ、設計および製造仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。</span><span class="sxs-lookup"><span data-stu-id="6282f-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="6282f-138">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="6282f-138">Security management</span></span>

  <span data-ttu-id="6282f-139">セキュリティの状態を監視し、リアルタイムで脅威を検出して対応できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6282f-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="6282f-140">リモート/モバイル アクセスおよびビジネス パートナー:</span><span class="sxs-lookup"><span data-stu-id="6282f-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="6282f-141">リモート ワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="6282f-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="6282f-142">持ち込みデバイス (BYOD) と会社所有のデバイスの管理に着手し、確実にアクセスをセキュリティで保護し、アプリケーションを正しく動作させ、企業データを保護できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6282f-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="6282f-143">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="6282f-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="6282f-144">よくアクセスされているリソースをクラウドに移動することで、保守作業とサポートのコストを削減し、リモート アクセス ソリューションのパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="6282f-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="6282f-145">企業間 (B2B) のトランザクションにおける接続性を向上し、オーバーヘッドを削減する</span><span class="sxs-lookup"><span data-stu-id="6282f-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="6282f-146">老朽化が進み、維持にコストがかかるパートナー エクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6282f-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="6282f-147">コンプライアンス:</span><span class="sxs-lookup"><span data-stu-id="6282f-147">Compliance:</span></span>

- <span data-ttu-id="6282f-148">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="6282f-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="6282f-149">欧州連合の一般データ保護規則 (GDPR) などのデータ ストレージ、暗号化、データ プライバシー、個人データの規制に関する産業および地域の規則に準拠し、これを維持します。</span><span class="sxs-lookup"><span data-stu-id="6282f-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="6282f-150">管理:</span><span class="sxs-lookup"><span data-stu-id="6282f-150">Management:</span></span>

- <span data-ttu-id="6282f-151">クライアント PC とデバイスで実行されているソフトウェアを管理するために、IT オーバーヘッドを削減します。</span><span class="sxs-lookup"><span data-stu-id="6282f-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="6282f-152">組織全体で Windows オペレーティング システムと Microsoft Office ProPlus への更新プログラムのインストールを自動化します。</span><span class="sxs-lookup"><span data-stu-id="6282f-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="6282f-153">Contoso 社のビジネス ニーズを Microsoft 365 Enterprise にマッピングする</span><span class="sxs-lookup"><span data-stu-id="6282f-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6282f-154">Contoso 社の IT 部門は、展開に先立って次のビジネス ニーズを Microsoft 365 Enterprise E5 の機能にマッピングすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="6282f-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="6282f-155">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="6282f-155">**Category**</span></span> | <span data-ttu-id="6282f-156">**ビジネス ニーズ**</span><span class="sxs-lookup"><span data-stu-id="6282f-156">**Business need**</span></span> | <span data-ttu-id="6282f-157">**Microsoft 365 Enterprise の製品または機能**</span><span class="sxs-lookup"><span data-stu-id="6282f-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="6282f-158">生産性</span><span class="sxs-lookup"><span data-stu-id="6282f-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="6282f-159">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="6282f-159">Make collaboration easier</span></span> | <span data-ttu-id="6282f-160">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="6282f-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="6282f-161">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6282f-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="6282f-162">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="6282f-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6282f-163">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="6282f-163">Increase creativity and innovation</span></span> | <span data-ttu-id="6282f-164">Windows Ink、職場の Cortana、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6282f-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="6282f-165">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6282f-165">Security</span></span> |  |  |
|  | <span data-ttu-id="6282f-166">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="6282f-166">Identity & access management</span></span> | <span data-ttu-id="6282f-167">Azure 多要素認証 (MFA) および Azure AD Privileged Identity Management (PIM) 付きの専用のグローバル管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="6282f-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="6282f-168">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="6282f-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="6282f-169">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="6282f-169">Conditional access</span></span> <BR> <span data-ttu-id="6282f-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="6282f-170">Windows Hello</span></span> <BR> <span data-ttu-id="6282f-171">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="6282f-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="6282f-172">脅威保護</span><span class="sxs-lookup"><span data-stu-id="6282f-172">Threat protection</span></span> | <span data-ttu-id="6282f-173">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="6282f-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="6282f-174">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="6282f-174">Windows Defender</span></span> <BR> <span data-ttu-id="6282f-175">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6282f-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="6282f-176">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6282f-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="6282f-177">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="6282f-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="6282f-178">情報保護</span><span class="sxs-lookup"><span data-stu-id="6282f-178">Information protection</span></span> | <span data-ttu-id="6282f-179">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="6282f-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="6282f-180">Office 365 データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="6282f-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="6282f-181">Windows 情報保護 (WIP)</span><span class="sxs-lookup"><span data-stu-id="6282f-181">Windows Information Protection DataRecoveryCertificate</span></span> <BR> <span data-ttu-id="6282f-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6282f-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="6282f-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6282f-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6282f-184">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="6282f-184">Security management</span></span> | <span data-ttu-id="6282f-185">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="6282f-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="6282f-186">Windows Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="6282f-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="6282f-187">リモート/モバイル アクセスおよびビジネス パートナー</span><span class="sxs-lookup"><span data-stu-id="6282f-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="6282f-188">リモート ワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="6282f-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="6282f-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6282f-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6282f-190">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="6282f-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="6282f-191">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="6282f-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6282f-192">B2B のトランザクションにおける接続性を向上し、オーバーヘッドを削減する</span><span class="sxs-lookup"><span data-stu-id="6282f-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="6282f-193">フェデレーション認証とクラウドベースのリソース</span><span class="sxs-lookup"><span data-stu-id="6282f-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="6282f-194">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="6282f-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="6282f-195">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="6282f-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="6282f-196">Office 365 の GDPR 機能</span><span class="sxs-lookup"><span data-stu-id="6282f-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="6282f-197">管理</span><span class="sxs-lookup"><span data-stu-id="6282f-197">Management</span></span> |  |  |
|  | <span data-ttu-id="6282f-198">クライアントの更新プログラムをインストールするため、IT オーバーヘッドを削減する</span><span class="sxs-lookup"><span data-stu-id="6282f-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="6282f-199">展開リング</span><span class="sxs-lookup"><span data-stu-id="6282f-199">Deployment rings</span></span> <BR> <span data-ttu-id="6282f-200">Windows 10 Enterprise の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="6282f-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="6282f-201">Office 365 ProPlus の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="6282f-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="6282f-202">次の手順</span><span class="sxs-lookup"><span data-stu-id="6282f-202">Next step</span></span>

<span data-ttu-id="6282f-203">Contoso 社のオンプレミス ネットワークと、Microsoft 365 のクラウドベースのリソースへのアクセスと待ち時間を最適化した方法について[確認](contoso-networking.md)します。</span><span class="sxs-lookup"><span data-stu-id="6282f-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="6282f-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="6282f-204">See also</span></span>

[<span data-ttu-id="6282f-205">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="6282f-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6282f-206">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="6282f-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
