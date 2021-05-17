---
title: Contoso IT インフラストラクチャとビジネス ニーズ
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
description: Contoso のオンプレミス IT インフラストラクチャの基本的な構造と、企業のビジネス ニーズが企業向けサービスによってどのように満たされるかMicrosoft 365理解します。
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558408"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="98ef7-103">Contoso IT インフラストラクチャとビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="98ef7-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="98ef7-104">Contoso 社は、オンプレミスの集中管理された IT インフラストラクチャから、クラウドベースの個人の生産性ワークロードとアプリケーションを組み込んだクラウドを含むセットアップに移行しています。</span><span class="sxs-lookup"><span data-stu-id="98ef7-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="98ef7-105">既存の Contoso IT インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="98ef7-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="98ef7-106">Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="98ef7-107">アプリケーション データセンター、DMZ、およびインターネットを備え、本社のオフィスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![既存の Contoso IT インフラストラクチャ](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="98ef7-109">オンプレミス アプリケーション データセンターのホストは次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="98ef7-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="98ef7-110">他の Linux データベースを使用するカスタム SQL Serverアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="98ef7-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="98ef7-111">従来の SharePoint サーバーのセット。</span><span class="sxs-lookup"><span data-stu-id="98ef7-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="98ef7-112">ファイル記憶域用の組織およびチームレベルのサーバー。</span><span class="sxs-lookup"><span data-stu-id="98ef7-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="98ef7-113">さらに、各地域のハブ オフィスは、同様のアプリケーション セットを持つサーバー セットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="98ef7-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="98ef7-114">これらのサーバーは、地域の IT 部門が管理します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="98ef7-115">こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。</span><span class="sxs-lookup"><span data-stu-id="98ef7-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="98ef7-116">Contoso 本社 DMZ では、異なるサーバー セットで次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="98ef7-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="98ef7-117">顧客が製品、パーツ、消耗品、およびサービスを注文できる Contoso パブリック Web サイトのホスティング。</span><span class="sxs-lookup"><span data-stu-id="98ef7-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="98ef7-118">パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。</span><span class="sxs-lookup"><span data-stu-id="98ef7-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="98ef7-119">パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの仮想プライベート ネットワーク (VPN) ベースのリモート アクセス。</span><span class="sxs-lookup"><span data-stu-id="98ef7-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="98ef7-120">Contoso のビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="98ef7-120">Contoso business needs</span></span>

<span data-ttu-id="98ef7-121">Contoso のビジネス ニーズは、次の 5 つの主なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="98ef7-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="98ef7-122">**生産性**</span><span class="sxs-lookup"><span data-stu-id="98ef7-122">**Productivity**</span></span>

- <span data-ttu-id="98ef7-123">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="98ef7-123">Make collaboration easier</span></span>

  <span data-ttu-id="98ef7-124">電子メールとファイル共有ベースのコラボレーションを、ドキュメント、簡単なオンライン会議、およびキャプチャされた会話スレッドに対するリアルタイムの変更を可能にするオンライン モデルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="98ef7-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="98ef7-125">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="98ef7-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="98ef7-126">多くの従業員が自宅または現場で作業を行う場合、ボトルネックの VPN ソリューションをクラウド内の Contoso データおよびリソースへのパフォーマンスの高いアクセスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="98ef7-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="98ef7-127">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="98ef7-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="98ef7-128">手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。</span><span class="sxs-lookup"><span data-stu-id="98ef7-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="98ef7-129">**セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="98ef7-129">**Security**</span></span>

- <span data-ttu-id="98ef7-130">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="98ef7-130">Identity and access management</span></span>

  <span data-ttu-id="98ef7-131">多要素認証などの認証を適用し、ユーザーアカウントと管理者アカウントの資格情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="98ef7-132">脅威保護</span><span class="sxs-lookup"><span data-stu-id="98ef7-132">Threat protection</span></span>

  <span data-ttu-id="98ef7-133">メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="98ef7-134">情報保護</span><span class="sxs-lookup"><span data-stu-id="98ef7-134">Information protection</span></span>

  <span data-ttu-id="98ef7-135">顧客データ、設計および製造仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="98ef7-136">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="98ef7-136">Security management</span></span>

  <span data-ttu-id="98ef7-137">セキュリティの態勢を監視し、脅威をリアルタイムで検出して対応します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="98ef7-138">**リモート/モバイル アクセスおよびビジネス パートナー**</span><span class="sxs-lookup"><span data-stu-id="98ef7-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="98ef7-139">リモートワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="98ef7-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="98ef7-140">セキュリティで保護されたアクセス、適切なアプリケーション動作、および会社のデータ保護を確保するために、独自のデバイス (BYOD) と会社所有のデバイス管理を実装します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="98ef7-141">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="98ef7-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="98ef7-142">一般的にアクセスされるリソースをクラウドに移行することで、メンテナンスとサポートのコストを削減し、リモート アクセス ソリューションのパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="98ef7-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="98ef7-143">ビジネス間 (B2B) トランザクションに対する接続性の向上とオーバーヘッドの削減</span><span class="sxs-lookup"><span data-stu-id="98ef7-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="98ef7-144">エージングおよび高価なパートナー エクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに置き換える。</span><span class="sxs-lookup"><span data-stu-id="98ef7-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="98ef7-145">**コンプライアンス**</span><span class="sxs-lookup"><span data-stu-id="98ef7-145">**Compliance**</span></span>

- <span data-ttu-id="98ef7-146">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="98ef7-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="98ef7-147">欧州連合の一般データ保護規則 (GDPR) など、データストレージ、暗号化、データプライバシー、および個人データ規制に関する業界および地域の規制への準拠を確認します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="98ef7-148">**管理**</span><span class="sxs-lookup"><span data-stu-id="98ef7-148">**Management**</span></span>

- <span data-ttu-id="98ef7-149">クライアント PC およびデバイスで実行されているソフトウェアを管理するための IT オーバーヘッドを削減する</span><span class="sxs-lookup"><span data-stu-id="98ef7-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="98ef7-150">組織全体のオペレーティング システムとWindows更新プログラムMicrosoft 365 Apps for enterpriseインストールを自動化します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="98ef7-151">エンタープライズ向け Contoso ビジネスのMicrosoft 365マッピング</span><span class="sxs-lookup"><span data-stu-id="98ef7-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="98ef7-152">Contoso IT 部門は、展開前に次のビジネス ニーズのマッピングMicrosoft 365 E5を決定しました。</span><span class="sxs-lookup"><span data-stu-id="98ef7-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="98ef7-153">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="98ef7-153">Category</span></span> | <span data-ttu-id="98ef7-154">ビジネス ニーズ</span><span class="sxs-lookup"><span data-stu-id="98ef7-154">Business need</span></span> | <span data-ttu-id="98ef7-155">Microsoft 365製品または機能の詳細</span><span class="sxs-lookup"><span data-stu-id="98ef7-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="98ef7-156">生産性</span><span class="sxs-lookup"><span data-stu-id="98ef7-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="98ef7-157">グループ作業を容易にする</span><span class="sxs-lookup"><span data-stu-id="98ef7-157">Make collaboration easier</span></span> | <span data-ttu-id="98ef7-158">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="98ef7-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="98ef7-159">リモート ワーカーとモバイル ワーカーの生産性を向上させる</span><span class="sxs-lookup"><span data-stu-id="98ef7-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="98ef7-160">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="98ef7-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="98ef7-161">独創性と革新性を向上させる</span><span class="sxs-lookup"><span data-stu-id="98ef7-161">Increase creativity and innovation</span></span> | <span data-ttu-id="98ef7-162">Windows Ink、職場の Cortana、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="98ef7-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="98ef7-163">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="98ef7-163">Security</span></span> |  |  |
|  | <span data-ttu-id="98ef7-164">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="98ef7-164">Identity & access management</span></span> | <span data-ttu-id="98ef7-165">Azure AD 多要素認証 (MFA) と Azure AD Privileged Identity Management (PIM) を使用した専用のグローバル管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="98ef7-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="98ef7-166">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="98ef7-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="98ef7-167">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="98ef7-167">Conditional Access</span></span> <BR> <span data-ttu-id="98ef7-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="98ef7-168">Windows Hello</span></span> <BR> <span data-ttu-id="98ef7-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="98ef7-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="98ef7-170">脅威保護</span><span class="sxs-lookup"><span data-stu-id="98ef7-170">Threat protection</span></span> | <span data-ttu-id="98ef7-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="98ef7-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="98ef7-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="98ef7-172">Windows Defender</span></span> <BR> <span data-ttu-id="98ef7-173">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="98ef7-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="98ef7-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="98ef7-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="98ef7-175">Microsoft 365の調査と対応</span><span class="sxs-lookup"><span data-stu-id="98ef7-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="98ef7-176">情報保護</span><span class="sxs-lookup"><span data-stu-id="98ef7-176">Information protection</span></span> | <span data-ttu-id="98ef7-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="98ef7-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="98ef7-178">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="98ef7-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="98ef7-179">Windows 情報保護 (WIP)</span><span class="sxs-lookup"><span data-stu-id="98ef7-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="98ef7-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="98ef7-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="98ef7-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="98ef7-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="98ef7-182">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="98ef7-182">Security management</span></span> | <span data-ttu-id="98ef7-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="98ef7-183">Azure Defender</span></span>  <BR> <span data-ttu-id="98ef7-184">Windows Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="98ef7-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="98ef7-185">リモート/モバイル アクセスおよびビジネス パートナー</span><span class="sxs-lookup"><span data-stu-id="98ef7-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="98ef7-186">リモート ワーカーとモバイル ワーカーのセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="98ef7-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="98ef7-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="98ef7-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="98ef7-188">従業員のリモート アクセス インフラストラクチャを縮小する</span><span class="sxs-lookup"><span data-stu-id="98ef7-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="98ef7-189">Microsoft 365 のワークロードとクラウドベースのデータ</span><span class="sxs-lookup"><span data-stu-id="98ef7-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="98ef7-190">B2B トランザクションの接続性とオーバーヘッドの削減</span><span class="sxs-lookup"><span data-stu-id="98ef7-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="98ef7-191">フェデレーション認証とクラウドベースのリソース</span><span class="sxs-lookup"><span data-stu-id="98ef7-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="98ef7-192">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="98ef7-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="98ef7-193">地域の規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="98ef7-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="98ef7-194">GDPR の機能 (Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98ef7-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="98ef7-195">管理</span><span class="sxs-lookup"><span data-stu-id="98ef7-195">Management</span></span> |  |  |
|  | <span data-ttu-id="98ef7-196">クライアント更新プログラムのインストールに関する IT オーバーヘッドの削減</span><span class="sxs-lookup"><span data-stu-id="98ef7-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="98ef7-197">Windows 10 Enterprise の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="98ef7-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="98ef7-198">Microsoft 365 Apps for enterprise の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="98ef7-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="98ef7-199">次の手順</span><span class="sxs-lookup"><span data-stu-id="98ef7-199">Next step</span></span>

<span data-ttu-id="98ef7-200">Contoso Corporation のオンプレミス[ネットワーク](contoso-networking.md)と、クラウド ベースのリソースへのアクセスと待機時間を最適化Microsoft 365について説明します。</span><span class="sxs-lookup"><span data-stu-id="98ef7-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="98ef7-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="98ef7-201">See also</span></span>

[<span data-ttu-id="98ef7-202">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="98ef7-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="98ef7-203">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="98ef7-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
