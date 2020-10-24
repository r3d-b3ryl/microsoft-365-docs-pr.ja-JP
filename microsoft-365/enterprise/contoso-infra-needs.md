---
title: Contoso IT インフラストラクチャとビジネスニーズ
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のオンプレミスの IT インフラストラクチャの基本構造と、企業のビジネスニーズが Microsoft 365 for enterprise によってどのように満たされるかについて説明します。
ms.openlocfilehash: 767374097efa116f116cff6f6ddf96d075eb71ed
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754588"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="66f40-103">Contoso IT インフラストラクチャとビジネスニーズ</span><span class="sxs-lookup"><span data-stu-id="66f40-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="66f40-104">Contoso 社は、オンプレミスの集中管理された IT インフラストラクチャから、クラウドベースの個人の生産性のワークロードとアプリケーションを組み込んだクラウドを含むセットアップに移行しています。</span><span class="sxs-lookup"><span data-stu-id="66f40-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="66f40-105">既存の Contoso IT インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="66f40-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="66f40-106">Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。</span><span class="sxs-lookup"><span data-stu-id="66f40-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="66f40-107">ここでは、アプリケーションデータセンター、DMZ、およびインターネットを使用した本社オフィスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66f40-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![既存の Contoso IT インフラストラクチャ](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="66f40-109">オンプレミス アプリケーション データセンターのホストは次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="66f40-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="66f40-110">SQL Server およびその他の Linux データベースを使用するカスタムの基幹業務アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="66f40-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="66f40-111">従来の SharePoint サーバーのセット。</span><span class="sxs-lookup"><span data-stu-id="66f40-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="66f40-112">ファイル記憶域用の組織およびチームレベルのサーバー。</span><span class="sxs-lookup"><span data-stu-id="66f40-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="66f40-113">さらに、各地域のハブ オフィスは、同様のアプリケーション セットを持つサーバー セットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="66f40-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="66f40-114">これらのサーバーは、地域の IT 部門が管理します。</span><span class="sxs-lookup"><span data-stu-id="66f40-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="66f40-115">こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。</span><span class="sxs-lookup"><span data-stu-id="66f40-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="66f40-116">Contoso 本社 DMZ では、サーバーのさまざまなセットが次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="66f40-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="66f40-117">顧客が製品、パーツ、備品、サービスを注文できる Contoso 社のパブリック web サイトのホスティング。</span><span class="sxs-lookup"><span data-stu-id="66f40-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="66f40-118">パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。</span><span class="sxs-lookup"><span data-stu-id="66f40-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="66f40-119">パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの仮想プライベート ネットワーク (VPN) ベースのリモート アクセス。</span><span class="sxs-lookup"><span data-stu-id="66f40-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="66f40-120">Contoso 社のビジネスニーズ</span><span class="sxs-lookup"><span data-stu-id="66f40-120">Contoso business needs</span></span>

<span data-ttu-id="66f40-121">Contoso 社のビジネスニーズは、次の5つの主要なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="66f40-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="66f40-122">**生産性**</span><span class="sxs-lookup"><span data-stu-id="66f40-122">**Productivity**</span></span>

- <span data-ttu-id="66f40-123">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="66f40-123">Make collaboration easier</span></span>

  <span data-ttu-id="66f40-124">電子メールとファイル共有ベースのコラボレーションをオンラインモデルに置き換えて、ドキュメントのリアルタイム変更、オンライン会議の簡単な変更、およびキャプチャされた会話スレッドを可能にします。</span><span class="sxs-lookup"><span data-stu-id="66f40-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="66f40-125">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="66f40-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="66f40-126">多くの従業員が自宅または現場で働いている場合は、ボトルネック VPN ソリューションを、クラウド内の Contoso データおよびリソースへの良好なアクセスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="66f40-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="66f40-127">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="66f40-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="66f40-128">手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。</span><span class="sxs-lookup"><span data-stu-id="66f40-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="66f40-129">**セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="66f40-129">**Security**</span></span>

- <span data-ttu-id="66f40-130">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="66f40-130">Identity and access management</span></span>

  <span data-ttu-id="66f40-131">多元的およびその他の形式の認証を適用し、ユーザーと管理者のアカウントの資格情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="66f40-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="66f40-132">脅威保護</span><span class="sxs-lookup"><span data-stu-id="66f40-132">Threat protection</span></span>

  <span data-ttu-id="66f40-133">メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="66f40-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="66f40-134">情報保護</span><span class="sxs-lookup"><span data-stu-id="66f40-134">Information protection</span></span>

  <span data-ttu-id="66f40-135">顧客データ、設計および製造仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。</span><span class="sxs-lookup"><span data-stu-id="66f40-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="66f40-136">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="66f40-136">Security management</span></span>

  <span data-ttu-id="66f40-137">セキュリティの状況を監視し、リアルタイムで脅威を検出して対応します。</span><span class="sxs-lookup"><span data-stu-id="66f40-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="66f40-138">**リモート/モバイル アクセスおよびビジネス パートナー**</span><span class="sxs-lookup"><span data-stu-id="66f40-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="66f40-139">リモートワーカーとモバイルワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="66f40-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="66f40-140">を実装する独自のデバイス (BYOD) および会社所有のデバイス管理を利用して、セキュリティで保護されたアクセス、適切なアプリケーションの動作、および会社のデータ保護を確保します。</span><span class="sxs-lookup"><span data-stu-id="66f40-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="66f40-141">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="66f40-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="66f40-142">一般的にアクセスされるリソースをクラウドに移行することによって、メンテナンスとサポートのコストを削減し、リモートアクセスソリューションのパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="66f40-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="66f40-143">Susiness (B2B) トランザクションに対して、接続性を向上させると共にオーバーヘッドを軽減する</span><span class="sxs-lookup"><span data-stu-id="66f40-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="66f40-144">エージングと高価なパートナーエクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="66f40-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="66f40-145">**コンプライアンス**</span><span class="sxs-lookup"><span data-stu-id="66f40-145">**Compliance**</span></span>

- <span data-ttu-id="66f40-146">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="66f40-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="66f40-147">欧州連合の一般的なデータ保護規則 (GDPR) など、データストレージ、暗号化、データプライバシー、および個人データの規制に関する業界および地域の規制に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f40-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="66f40-148">**管理**</span><span class="sxs-lookup"><span data-stu-id="66f40-148">**Management**</span></span>

- <span data-ttu-id="66f40-149">クライアント Pc およびデバイス上で実行されているソフトウェアを管理するための IT オーバーヘッドの削減</span><span class="sxs-lookup"><span data-stu-id="66f40-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="66f40-150">組織全体にわたって、Windows オペレーティングシステムと Microsoft 365 アプリに対する更新プログラムのインストールを自動化します。</span><span class="sxs-lookup"><span data-stu-id="66f40-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="66f40-151">エンタープライズ向けに Contoso のビジネスニーズを Microsoft 365 にマッピングする</span><span class="sxs-lookup"><span data-stu-id="66f40-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="66f40-152">Contoso 社の IT 部門は、展開する前に、次のビジネスニーズを Microsoft 365 E5 機能にマッピングすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="66f40-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="66f40-153">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="66f40-153">Category</span></span> | <span data-ttu-id="66f40-154">ビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="66f40-154">Business need</span></span> | <span data-ttu-id="66f40-155">エンタープライズ製品または機能のための Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="66f40-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="66f40-156">生産性</span><span class="sxs-lookup"><span data-stu-id="66f40-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="66f40-157">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="66f40-157">Make collaboration easier</span></span> | <span data-ttu-id="66f40-158">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="66f40-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="66f40-159">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="66f40-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="66f40-160">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="66f40-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="66f40-161">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="66f40-161">Increase creativity and innovation</span></span> | <span data-ttu-id="66f40-162">Windows Ink、職場の Cortana、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="66f40-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="66f40-163">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="66f40-163">Security</span></span> |  |  |
|  | <span data-ttu-id="66f40-164">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="66f40-164">Identity & access management</span></span> | <span data-ttu-id="66f40-165">Azure 多要素認証 (MFA) と Azure Active Directory の特権 Id 管理 (PIM) を使用した専用のグローバル管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="66f40-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="66f40-166">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="66f40-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="66f40-167">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="66f40-167">Conditional Access</span></span> <BR> <span data-ttu-id="66f40-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="66f40-168">Windows Hello</span></span> <BR> <span data-ttu-id="66f40-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="66f40-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="66f40-170">脅威保護</span><span class="sxs-lookup"><span data-stu-id="66f40-170">Threat protection</span></span> | <span data-ttu-id="66f40-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="66f40-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="66f40-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="66f40-172">Windows Defender</span></span> <BR> <span data-ttu-id="66f40-173">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66f40-173">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="66f40-174">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66f40-174">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="66f40-175">Microsoft 365 脅威の調査と応答</span><span class="sxs-lookup"><span data-stu-id="66f40-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="66f40-176">情報保護</span><span class="sxs-lookup"><span data-stu-id="66f40-176">Information protection</span></span> | <span data-ttu-id="66f40-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="66f40-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="66f40-178">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="66f40-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="66f40-179">Windows 情報保護 (WIP)</span><span class="sxs-lookup"><span data-stu-id="66f40-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="66f40-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="66f40-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="66f40-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="66f40-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="66f40-182">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="66f40-182">Security management</span></span> | <span data-ttu-id="66f40-183">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="66f40-183">Azure Security Center</span></span>  <BR> <span data-ttu-id="66f40-184">Windows Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="66f40-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="66f40-185">リモート/モバイル アクセスおよびビジネス パートナー</span><span class="sxs-lookup"><span data-stu-id="66f40-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="66f40-186">リモート ワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="66f40-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="66f40-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="66f40-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="66f40-188">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="66f40-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="66f40-189">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="66f40-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="66f40-190">B2B トランザクションの接続性を向上し、オーバーヘッドを軽減する</span><span class="sxs-lookup"><span data-stu-id="66f40-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="66f40-191">フェデレーション認証とクラウドベースのリソース</span><span class="sxs-lookup"><span data-stu-id="66f40-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="66f40-192">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="66f40-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="66f40-193">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="66f40-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="66f40-194">Microsoft 365 の GDPR 機能</span><span class="sxs-lookup"><span data-stu-id="66f40-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="66f40-195">管理</span><span class="sxs-lookup"><span data-stu-id="66f40-195">Management</span></span> |  |  |
|  | <span data-ttu-id="66f40-196">クライアント更新プログラムをインストールするための IT オーバーヘッドを軽減する</span><span class="sxs-lookup"><span data-stu-id="66f40-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="66f40-197">Windows 10 Enterprise の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="66f40-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="66f40-198">Microsoft 365 Apps for enterprise の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="66f40-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="66f40-199">次の手順</span><span class="sxs-lookup"><span data-stu-id="66f40-199">Next step</span></span>

<span data-ttu-id="66f40-200">Contoso 社 [のオンプレミスネットワーク](contoso-networking.md) について、および Microsoft 365 クラウドベースのリソースへのアクセスと遅延に対してどのように最適化されたかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66f40-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="66f40-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="66f40-201">See also</span></span>

[<span data-ttu-id="66f40-202">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="66f40-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="66f40-203">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="66f40-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
