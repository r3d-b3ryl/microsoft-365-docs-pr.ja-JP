---
title: Contoso IT インフラストラクチャとビジネスニーズ
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のオンプレミスの IT インフラストラクチャの基本構造と、企業のビジネスニーズが Microsoft 365 for enterprise によってどのように満たされるかについて説明します。
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637177"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="90a08-103">Contoso IT インフラストラクチャとビジネスニーズ</span><span class="sxs-lookup"><span data-stu-id="90a08-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="90a08-104">Contoso 社は、オンプレミスの集中管理された IT インフラストラクチャから、クラウドベースの個人の生産性のワークロードとアプリケーションを組み込んだクラウドを含むセットアップに移行しています。</span><span class="sxs-lookup"><span data-stu-id="90a08-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="90a08-105">既存の Contoso IT インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="90a08-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="90a08-106">Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。</span><span class="sxs-lookup"><span data-stu-id="90a08-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="90a08-107">図1は、本社とアプリケーションデータセンター、DMZ、およびインターネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="90a08-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![既存の Contoso IT インフラストラクチャ](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="90a08-109">**図 1: 既存の Contoso IT infrastructure**</span><span class="sxs-lookup"><span data-stu-id="90a08-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="90a08-110">オンプレミス アプリケーション データセンターのホストは次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="90a08-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="90a08-111">SQL Server およびその他の Linux データベースを使用するカスタムの基幹業務アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="90a08-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="90a08-112">従来の SharePoint サーバーのセット。</span><span class="sxs-lookup"><span data-stu-id="90a08-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="90a08-113">ファイル記憶域用の組織およびチームレベルのサーバー。</span><span class="sxs-lookup"><span data-stu-id="90a08-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="90a08-114">さらに、各地域のハブ オフィスは、同様のアプリケーション セットを持つサーバー セットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="90a08-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="90a08-115">これらのサーバーは、地域の IT 部門が管理します。</span><span class="sxs-lookup"><span data-stu-id="90a08-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="90a08-116">こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。</span><span class="sxs-lookup"><span data-stu-id="90a08-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="90a08-117">Contoso 本社 DMZ では、サーバーのさまざまなセットが次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="90a08-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="90a08-118">顧客が製品、パーツ、備品、サービスを注文できる Contoso 社のパブリック web サイトのホスティング。</span><span class="sxs-lookup"><span data-stu-id="90a08-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="90a08-119">パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。</span><span class="sxs-lookup"><span data-stu-id="90a08-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="90a08-120">パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの仮想プライベート ネットワーク (VPN) ベースのリモート アクセス。</span><span class="sxs-lookup"><span data-stu-id="90a08-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="90a08-121">Contoso 社のビジネスニーズ</span><span class="sxs-lookup"><span data-stu-id="90a08-121">Contoso business needs</span></span>

<span data-ttu-id="90a08-122">Contoso 社のビジネスニーズは、次の5つの主要なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="90a08-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="90a08-123">**生産性**</span><span class="sxs-lookup"><span data-stu-id="90a08-123">**Productivity**</span></span>

- <span data-ttu-id="90a08-124">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="90a08-124">Make collaboration easier</span></span>

  <span data-ttu-id="90a08-125">電子メールとファイル共有ベースのコラボレーションをオンラインモデルに置き換えて、ドキュメントのリアルタイム変更、オンライン会議の簡単な変更、およびキャプチャされた会話スレッドを可能にします。</span><span class="sxs-lookup"><span data-stu-id="90a08-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="90a08-126">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="90a08-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="90a08-127">多くの従業員が自宅または現場で働いている場合は、ボトルネック VPN ソリューションを、クラウド内の Contoso データおよびリソースへの良好なアクセスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="90a08-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="90a08-128">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="90a08-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="90a08-129">手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。</span><span class="sxs-lookup"><span data-stu-id="90a08-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="90a08-130">**セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="90a08-130">**Security**</span></span>

- <span data-ttu-id="90a08-131">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="90a08-131">Identity and access management</span></span>

  <span data-ttu-id="90a08-132">多元的およびその他の形式の認証を適用し、ユーザーと管理者のアカウントの資格情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="90a08-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="90a08-133">脅威保護</span><span class="sxs-lookup"><span data-stu-id="90a08-133">Threat protection</span></span>

  <span data-ttu-id="90a08-134">メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="90a08-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="90a08-135">情報保護</span><span class="sxs-lookup"><span data-stu-id="90a08-135">Information protection</span></span>

  <span data-ttu-id="90a08-136">顧客データ、設計および製造仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。</span><span class="sxs-lookup"><span data-stu-id="90a08-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="90a08-137">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="90a08-137">Security management</span></span>

  <span data-ttu-id="90a08-138">セキュリティの状況を監視し、リアルタイムで脅威を検出して対応します。</span><span class="sxs-lookup"><span data-stu-id="90a08-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="90a08-139">**リモート/モバイル アクセスおよびビジネス パートナー**</span><span class="sxs-lookup"><span data-stu-id="90a08-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="90a08-140">リモートワーカーとモバイルワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="90a08-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="90a08-141">を実装する独自のデバイス (BYOD) および会社所有のデバイス管理を利用して、セキュリティで保護されたアクセス、適切なアプリケーションの動作、および会社のデータ保護を確保します。</span><span class="sxs-lookup"><span data-stu-id="90a08-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="90a08-142">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="90a08-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="90a08-143">一般的にアクセスされるリソースをクラウドに移行することによって、メンテナンスとサポートのコストを削減し、リモートアクセスソリューションのパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="90a08-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="90a08-144">Susiness (B2B) トランザクションに対して、接続性を向上させると共にオーバーヘッドを軽減する</span><span class="sxs-lookup"><span data-stu-id="90a08-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="90a08-145">エージングと高価なパートナーエクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="90a08-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="90a08-146">**コンプライアンス**</span><span class="sxs-lookup"><span data-stu-id="90a08-146">**Compliance**</span></span>

- <span data-ttu-id="90a08-147">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="90a08-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="90a08-148">欧州連合の一般的なデータ保護規則 (GDPR) など、データストレージ、暗号化、データプライバシー、および個人データの規制に関する業界および地域の規制に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90a08-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="90a08-149">**管理**</span><span class="sxs-lookup"><span data-stu-id="90a08-149">**Management**</span></span>

- <span data-ttu-id="90a08-150">クライアント Pc およびデバイス上で実行されているソフトウェアを管理するための IT オーバーヘッドの削減</span><span class="sxs-lookup"><span data-stu-id="90a08-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="90a08-151">組織全体にわたって、Windows オペレーティングシステムと Microsoft 365 アプリに対する更新プログラムのインストールを自動化します。</span><span class="sxs-lookup"><span data-stu-id="90a08-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="90a08-152">エンタープライズ向けに Contoso のビジネスニーズを Microsoft 365 にマッピングする</span><span class="sxs-lookup"><span data-stu-id="90a08-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="90a08-153">Contoso 社の IT 部門は、展開する前に、次のビジネスニーズを Microsoft 365 E5 機能にマッピングすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="90a08-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="90a08-154">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="90a08-154">Category</span></span> | <span data-ttu-id="90a08-155">ビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="90a08-155">Business need</span></span> | <span data-ttu-id="90a08-156">エンタープライズ製品または機能のための Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90a08-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="90a08-157">生産性</span><span class="sxs-lookup"><span data-stu-id="90a08-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="90a08-158">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="90a08-158">Make collaboration easier</span></span> | <span data-ttu-id="90a08-159">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="90a08-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="90a08-160">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="90a08-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="90a08-161">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="90a08-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="90a08-162">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="90a08-162">Increase creativity and innovation</span></span> | <span data-ttu-id="90a08-163">Windows Ink、職場の Cortana、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="90a08-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="90a08-164">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="90a08-164">Security</span></span> |  |  |
|  | <span data-ttu-id="90a08-165">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="90a08-165">Identity & access management</span></span> | <span data-ttu-id="90a08-166">Azure 多要素認証 (MFA) と Azure Active Directory の特権 Id 管理 (PIM) を使用した専用のグローバル管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="90a08-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="90a08-167">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="90a08-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="90a08-168">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="90a08-168">Conditional Access</span></span> <BR> <span data-ttu-id="90a08-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="90a08-169">Windows Hello</span></span> <BR> <span data-ttu-id="90a08-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="90a08-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="90a08-171">脅威保護</span><span class="sxs-lookup"><span data-stu-id="90a08-171">Threat protection</span></span> | <span data-ttu-id="90a08-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="90a08-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="90a08-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="90a08-173">Windows Defender</span></span> <BR> <span data-ttu-id="90a08-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90a08-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="90a08-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90a08-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="90a08-176">Microsoft 365 脅威の調査と応答</span><span class="sxs-lookup"><span data-stu-id="90a08-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="90a08-177">情報保護</span><span class="sxs-lookup"><span data-stu-id="90a08-177">Information protection</span></span> | <span data-ttu-id="90a08-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="90a08-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="90a08-179">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="90a08-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="90a08-180">Windows 情報保護 (WIP)</span><span class="sxs-lookup"><span data-stu-id="90a08-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="90a08-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="90a08-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="90a08-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="90a08-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="90a08-183">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="90a08-183">Security management</span></span> | <span data-ttu-id="90a08-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="90a08-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="90a08-185">Windows Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="90a08-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="90a08-186">リモート/モバイル アクセスおよびビジネス パートナー</span><span class="sxs-lookup"><span data-stu-id="90a08-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="90a08-187">リモート ワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="90a08-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="90a08-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="90a08-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="90a08-189">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="90a08-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="90a08-190">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="90a08-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="90a08-191">B2B トランザクションの接続性を向上し、オーバーヘッドを軽減する</span><span class="sxs-lookup"><span data-stu-id="90a08-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="90a08-192">フェデレーション認証とクラウドベースのリソース</span><span class="sxs-lookup"><span data-stu-id="90a08-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="90a08-193">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="90a08-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="90a08-194">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="90a08-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="90a08-195">Microsoft 365 の GDPR 機能</span><span class="sxs-lookup"><span data-stu-id="90a08-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="90a08-196">管理</span><span class="sxs-lookup"><span data-stu-id="90a08-196">Management</span></span> |  |  |
|  | <span data-ttu-id="90a08-197">クライアント更新プログラムをインストールするための IT オーバーヘッドを軽減する</span><span class="sxs-lookup"><span data-stu-id="90a08-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="90a08-198">展開リング</span><span class="sxs-lookup"><span data-stu-id="90a08-198">Deployment rings</span></span> <BR> <span data-ttu-id="90a08-199">Windows 10 Enterprise の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="90a08-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="90a08-200">Microsoft 365 Apps for enterprise の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="90a08-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="90a08-201">次の手順</span><span class="sxs-lookup"><span data-stu-id="90a08-201">Next step</span></span>

<span data-ttu-id="90a08-202">Contoso 社のオンプレミスネットワークについて、および Microsoft 365 クラウドベースのリソースへのアクセスと遅延に対してどのように最適化されたかについて[説明](contoso-networking.md)します。</span><span class="sxs-lookup"><span data-stu-id="90a08-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="90a08-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="90a08-203">See also</span></span>

[<span data-ttu-id="90a08-204">Microsoft 365 for Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="90a08-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="90a08-205">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="90a08-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
