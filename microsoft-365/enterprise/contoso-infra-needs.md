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
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contoso IT インフラストラクチャとビジネスニーズ

Contoso 社は、オンプレミスの集中管理された IT インフラストラクチャから、クラウドベースの個人の生産性のワークロードとアプリケーションを組み込んだクラウドを含むセットアップに移行しています。

## <a name="existing-contoso-it-infrastructure"></a>既存の Contoso IT インフラストラクチャ

Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。

ここでは、アプリケーションデータセンター、DMZ、およびインターネットを使用した本社オフィスについて説明します。

![既存の Contoso IT インフラストラクチャ](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

オンプレミス アプリケーション データセンターのホストは次のとおりです: 

- SQL Server およびその他の Linux データベースを使用するカスタムの基幹業務アプリケーション。
- 従来の SharePoint サーバーのセット。
- ファイル記憶域用の組織およびチームレベルのサーバー。

さらに、各地域のハブ オフィスは、同様のアプリケーション セットを持つサーバー セットをサポートしています。 これらのサーバーは、地域の IT 部門が管理します。

こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。

Contoso 本社 DMZ では、サーバーのさまざまなセットが次の機能を提供します。

- 顧客が製品、パーツ、備品、サービスを注文できる Contoso 社のパブリック web サイトのホスティング。
- パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。
- パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの仮想プライベート ネットワーク (VPN) ベースのリモート アクセス。

## <a name="contoso-business-needs"></a>Contoso 社のビジネスニーズ

Contoso 社のビジネスニーズは、次の5つの主要なカテゴリに分類されます。

**生産性**

- グループ作業を容易にする

  電子メールとファイル共有ベースのコラボレーションをオンラインモデルに置き換えて、ドキュメントのリアルタイム変更、オンライン会議の簡単な変更、およびキャプチャされた会話スレッドを可能にします。
- リモート ワーカーとモバイル ワーカーの生産性を向上させる

  多くの従業員が自宅または現場で働いている場合は、ボトルネック VPN ソリューションを、クラウド内の Contoso データおよびリソースへの良好なアクセスに置き換えます。
- 独創性と革新性を向上させる

  手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。

**セキュリティ**

- ID およびアクセス管理

  多元的およびその他の形式の認証を適用し、ユーザーと管理者のアカウントの資格情報を保護します。

- 脅威保護

  メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。

- 情報保護

  顧客データ、設計および製造仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。

- セキュリティ管理

  セキュリティの状況を監視し、リアルタイムで脅威を検出して対応します。

**リモート/モバイル アクセスおよびビジネス パートナー**

- リモートワーカーとモバイルワーカーのセキュリティを強化する

  を実装する独自のデバイス (BYOD) および会社所有のデバイス管理を利用して、セキュリティで保護されたアクセス、適切なアプリケーションの動作、および会社のデータ保護を確保します。

- 従業員のリモート アクセス インフラストラクチャを縮小する

  一般的にアクセスされるリソースをクラウドに移行することによって、メンテナンスとサポートのコストを削減し、リモートアクセスソリューションのパフォーマンスを向上させます。

- Susiness (B2B) トランザクションに対して、接続性を向上させると共にオーバーヘッドを軽減する

  エージングと高価なパートナーエクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに置き換えます。

**コンプライアンス**

- 地域の規制要件に準拠する

  欧州連合の一般的なデータ保護規則 (GDPR) など、データストレージ、暗号化、データプライバシー、および個人データの規制に関する業界および地域の規制に準拠していることを確認します。

**管理**

- クライアント Pc およびデバイス上で実行されているソフトウェアを管理するための IT オーバーヘッドの削減

  組織全体にわたって、Windows オペレーティングシステムと Microsoft 365 アプリに対する更新プログラムのインストールを自動化します。

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>エンタープライズ向けに Contoso のビジネスニーズを Microsoft 365 にマッピングする

Contoso 社の IT 部門は、展開する前に、次のビジネスニーズを Microsoft 365 E5 機能にマッピングすることを決定しました。


| カテゴリ | ビジネス ニーズ | エンタープライズ製品または機能のための Microsoft 365 |
|:-------|:-----|:-----|
| 生産性 |  |  |
|  | グループ作業を容易にする | Microsoft Teams、SharePoint、OneDrive |
|  | リモート ワーカーとモバイル ワーカーの生産性を向上させる | Microsoft 365 のワークロードとクラウドベースのデータ |
|  | 独創性と革新性を向上させる | Windows Ink、職場の Cortana、PowerPoint |
| セキュリティ |  |  |
|  | ID およびアクセス管理 | Azure 多要素認証 (MFA) と Azure Active Directory の特権 Id 管理 (PIM) を使用した専用のグローバル管理者アカウント <BR> すべてのユーザー アカウントの MFA <BR> 条件付きアクセス <BR> Windows Hello <BR> Windows Credential Guard |
|  | 脅威保護 | Advanced Threat Analytics <BR> Windows Defender <BR> Advanced Threat Protection <BR> Office 365 Advanced Threat Protection <BR> Microsoft 365 脅威の調査と応答 <BR> |
|  | 情報保護 | Azure Information Protection <BR> データ損失防止 (DLP) <BR> Windows 情報保護 (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | セキュリティ管理 | Azure Security Center  <BR> Windows Defender セキュリティ センター |
| リモート/モバイル アクセスおよびビジネス パートナー |  |  |
|  | リモート ワーカーとモバイル ワーカーのセキュリティを強化する | Microsoft Intune |
|  | 従業員のリモート アクセス インフラストラクチャを縮小する | Microsoft 365 のワークロードとクラウドベースのデータ |
|  | B2B トランザクションの接続性を向上し、オーバーヘッドを軽減する | フェデレーション認証とクラウドベースのリソース |
| コンプライアンス |  |  |
|  | 地域の規制要件に準拠する | Microsoft 365 の GDPR 機能 |
| 管理 |  |  |
|  | クライアント更新プログラムをインストールするための IT オーバーヘッドを軽減する | Windows 10 Enterprise の更新プログラム <BR> Microsoft 365 Apps for enterprise の更新プログラム |
||||

## <a name="next-step"></a>次の手順

Contoso 社 [のオンプレミスネットワーク](contoso-networking.md) について、および Microsoft 365 クラウドベースのリソースへのアクセスと遅延に対してどのように最適化されたかについて説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
