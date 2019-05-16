---
title: Contoso 社の IT インフラストラクチャおよびビジネス ニーズ
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のオンプレミスの IT インフラストラクチャの基本的な構造について、およびそのビジネス ニーズが Microsoft 365 Enterprise によってどのように満たされるかについて説明します。
ms.openlocfilehash: e50a2b17544c1a551d25dffd751d12aec1c15ecd
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072617"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>Contoso 社の IT インフラストラクチャおよびビジネス ニーズ

**概要:** Contoso 社のオンプレミスの IT インフラストラクチャの基本的な構造について、およびそのビジネス ニーズが Microsoft 365 Enterprise によってどのように満たされるかについて説明します。


Contoso 社は、集中管理されたオンプレミスの IT インフラストラクチャから、クラウド包括型の IT インフラストラクチャへと移行しています。後者には、クラウドベースの個人生産性のワークロードとアプリケーションが組み込まれています。

## <a name="contosos-existing-it-infrastructure"></a>Contoso 社の既存の IT インフラストラクチャ

Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。

図 1 は、本社とアプリケーション データセンター、境界ネットワーク、およびインターネットを示しています。

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**図 1: Contoso 社の既存の IT インフラストラクチャ**
 
オンプレミス アプリケーション データセンターのホストは次のとおりです: 

- SQL Server や他の Linux データベースを使用するカスタムの基幹業務アプリケーション。
- 従来の SharePoint サーバーのセット。
- ファイル記憶域用の組織およびチームレベルのサーバー。

さらには、同様のアプリケーション セットを持つサーバー セットをサポートする各地域ハブ オフィスです。これらのサーバーは地域の IT 部門の管理下にあります。

こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。

Contoso 社の本社の境界ネットワークでは、サーバーのさまざまなセットが次のことを実現します。

- パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの VPN ベースのリモート アクセス。
- 顧客が製品、部品、備品、またはサービスを発注できる Contoso 社のパブリック Web サイトのホスティング。
- パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。

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

  顧客データ、設計仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。

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

  組織全体で Windows オペレーティング システムと Microsoft Office の更新プログラムのインストールを自動化します。

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a>Contoso 社のビジネス ニーズを Microsoft 365 Enterprise にマッピングする

Contoso 社の IT 部門は、展開に先立って次のビジネス ニーズを Microsoft 365 Enterprise E5 の機能にマッピングすることを決定しました。

||||
|:-------|:-----|:-----|
| **カテゴリ** | **ビジネス ニーズ** | **Microsoft 365 Enterprise の製品または機能** |
| 生産性 |  |  |
|  | グループ作業を容易にする | Teams、SharePoint Online、Skype for Business Online |
|  | リモート ワーカーとモバイル ワーカーの生産性を向上させる | Office 365 のワークロードとクラウドベースのデータ |
|  | 独創性と革新性を向上させる | Windows Ink、職場の Cortana、PowerPoint |
| セキュリティ |  |  |
|  | ID およびアクセス管理 | 多要素認証 (MFA) および Azure AD Privileged Identity Management (PIM) 付きの専用のグローバル管理者アカウント <BR> すべてのユーザー アカウントの MFA <BR> 条件付きアクセス <BR> Windows Hello <BR> Windows Credential Guard |
|  | 脅威保護 | Advanced Threat Analytics <BR> Windows Defender <BR> Advanced Threat Protection <BR> Office 365 Advanced Threat Protection <BR> Office 365 脅威の調査および対応 <BR> |
|  | 情報保護 | Azure Information Protection <BR> Office 365 データ損失防止 (DLP) <BR> Windows 情報保護 <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | セキュリティ管理 | Azure Security Center  <BR> Windows Defender セキュリティ センター |
| リモート/モバイル アクセスおよびビジネス パートナー |  |  |
|  | リモート ワーカーとモバイル ワーカーのセキュリティを強化する | Microsoft Intune |
|  | 従業員のリモート アクセス インフラストラクチャを縮小する | Office 365 のワークロードとクラウドベースのデータ |
|  | B2B のトランザクションにおける接続性を向上し、オーバーヘッドを削減する | フェデレーション認証とクラウドベースのリソース |
| コンプライアンス |  |  |
|  | 地域の規制要件に準拠する | Office 365 の GDPR 機能 |
| 管理 |  |  |
|  | クライアントの更新プログラムをインストールするため、IT オーバーヘッドを削減する | 展開リング <BR> 適切な Windows 10 のアップグレードと Autopilot <BR> Office 365 ProPlus |
||||

## <a name="next-step"></a>次の手順

Contoso 社のオンプレミス ネットワークと、組織全体の Microsoft 365 のクラウドベースのリソースへのアクセスと待ち時間を最適化した方法について[確認](contoso-networking.md)します。

## <a name="see-also"></a>関連項目

[展開ガイド](deploy-microsoft-365-enterprise.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
