---
title: Contoso 社の IT インフラストラクチャおよびビジネス ニーズ
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
description: Contoso 社のオンプレミスの IT インフラストラクチャの基本的な構造について、およびそのビジネスニーズが Microsoft 365 for enterprise によってどのように満たされたかについて説明します。
ms.openlocfilehash: 3dd744a8d936307c61303bf8ba0f2f198af59d91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685832"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>Contoso 社の IT インフラストラクチャおよびビジネス ニーズ

Contoso 社は、集中管理されたオンプレミスの IT インフラストラクチャから、クラウド包括型の IT インフラストラクチャへと移行しています。後者には、クラウドベースの個人生産性のワークロードとアプリケーションが組み込まれています。

## <a name="contosos-existing-it-infrastructure"></a>Contoso 社の既存の IT インフラストラクチャ

Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。

図 1 は、本社とアプリケーション データセンター、境界ネットワーク、およびインターネットを示しています。

![Contoso 社の既存の IT インフラストラクチャ](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**図 1: Contoso 社の既存の IT インフラストラクチャ**
 
オンプレミス アプリケーション データセンターのホストは次のとおりです: 

- SQL Server や他の Linux データベースを使用するカスタムの基幹業務アプリケーション。
- 従来の SharePoint サーバーのセット。
- ファイル記憶域用の組織およびチームレベルのサーバー。

さらに、各地域のハブ オフィスは、同様のアプリケーション セットを持つサーバー セットをサポートしています。 これらのサーバーは、地域の IT 部門が管理します。

こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。

Contoso 社の本社の境界ネットワークでは、サーバーのさまざまなセットが次のことを実現します。

- 顧客が製品、部品、備品、またはサービスを発注できる Contoso 社のパブリック Web サイトのホスティング。
- パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。
- パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの仮想プライベート ネットワーク (VPN) ベースのリモート アクセス。

## <a name="contosos-business-needs"></a>Contoso 社のビジネス ニーズ

Contoso 社のビジネス ニーズは、5 つの主なカテゴリに分類されます。

生産性:

- グループ作業を容易にする

  メールとファイル共有ベースのグループ作業を、オンライン モデルに置き換えることで、文書のリアルタイム変更、簡単なオンライン会議、会話スレッドのキャプチャを可能にします。
- リモート ワーカーとモバイル ワーカーの生産性を向上させる

  多くの従業員が自宅や現場で働いているため、ボトルネックとなっている VPN ソリューションを、クラウド内の Contoso 社のデータとリソースへの効率的なアクセスに変更します。
- 独創性と革新性を向上させる

  手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。

セキュリティ:

- ID およびアクセス管理

  多要素認証および他の形式の認証を適用し、ユーザーおよび管理者アカウントの資格情報を保護します。

- 脅威保護

  メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。

- 情報保護

  顧客データ、設計および製造仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。

- セキュリティ管理

  セキュリティの状態を監視し、リアルタイムで脅威を検出して対応できるようにします。

リモート/モバイル アクセスおよびビジネス パートナー:

- リモート ワーカーとモバイル ワーカーのセキュリティを強化する

  持ち込みデバイス (BYOD) と会社所有のデバイスの管理に着手し、確実にアクセスをセキュリティで保護し、アプリケーションを正しく動作させ、企業データを保護できるようにします。

- 従業員のリモート アクセス インフラストラクチャを縮小する

  よくアクセスされているリソースをクラウドに移動することで、保守作業とサポートのコストを削減し、リモート アクセス ソリューションのパフォーマンスを向上させます。

- 企業間 (B2B) のトランザクションにおける接続性を向上し、オーバーヘッドを削減する

  老朽化が進み、維持にコストがかかるパートナー エクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに切り替えます。

コンプライアンス:

- 地域の規制要件に準拠する

  欧州連合の一般データ保護規則 (GDPR) などのデータ ストレージ、暗号化、データ プライバシー、個人データの規制に関する産業および地域の規則に準拠し、これを維持します。

管理:

- クライアント PC とデバイスで実行されているソフトウェアを管理するために、IT オーバーヘッドを削減します。

  組織全体で Windows オペレーティング システムと Microsoft 365 Apps for enterprise の更新プログラムのインストールを自動化します。

## <a name="mapping-contosos-business-needs-to-microsoft-365-for-enterprise"></a>Contoso 社のビジネスニーズをエンタープライズ向け Microsoft 365 にマッピングする

Contoso 社の IT 部門は展開に先立ち、Microsoft 365 E5 の機能への以下のビジネス ニーズのマッピングを決定しました。


| カテゴリ | ビジネス ニーズ | エンタープライズ製品または機能のための Microsoft 365 |
|:-------|:-----|:-----|
| 生産性 |  |  |
|  | グループ作業を容易にする | Microsoft Teams、SharePoint、OneDrive |
|  | リモート ワーカーとモバイル ワーカーの生産性を向上させる | Microsoft 365 のワークロードとクラウドベースのデータ |
|  | 独創性と革新性を向上させる | Windows Ink、職場の Cortana、PowerPoint |
| セキュリティ |  |  |
|  | ID およびアクセス管理 | Azure 多要素認証 (MFA) および Azure AD Privileged Identity Management (PIM) 付きの専用のグローバル管理者アカウント <BR> すべてのユーザー アカウントの MFA <BR> 条件付きアクセス <BR> Windows Hello <BR> Windows Credential Guard |
|  | 脅威保護 | Advanced Threat Analytics <BR> Windows Defender <BR> Advanced Threat Protection <BR> Office 365 Advanced Threat Protection <BR> Microsoft 365 脅威の調査と応答 <BR> |
|  | 情報保護 | Azure Information Protection <BR> データ損失防止 (DLP) <BR> Windows 情報保護 (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | セキュリティ管理 | Azure Security Center  <BR> Windows Defender セキュリティ センター |
| リモート/モバイル アクセスおよびビジネス パートナー |  |  |
|  | リモート ワーカーとモバイル ワーカーのセキュリティを強化する | Microsoft Intune |
|  | 従業員のリモート アクセス インフラストラクチャを縮小する | Microsoft 365 のワークロードとクラウドベースのデータ |
|  | B2B のトランザクションにおける接続性を向上し、オーバーヘッドを削減する | フェデレーション認証とクラウドベースのリソース |
| コンプライアンス |  |  |
|  | 地域の規制要件に準拠する | Microsoft 365 の GDPR 機能 |
| 管理 |  |  |
|  | クライアントの更新プログラムをインストールするため、IT オーバーヘッドを削減する | 展開リング <BR> Windows 10 Enterprise の更新プログラム <BR> Microsoft 365 Apps for enterprise の更新プログラム |
||||

## <a name="next-step"></a>次の手順

Contoso 社のオンプレミス ネットワークと、Microsoft 365 のクラウドベースのリソースへのアクセスと待ち時間を最適化した方法について[確認](contoso-networking.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
