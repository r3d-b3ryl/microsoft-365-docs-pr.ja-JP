---
title: Contoso の IT インフラストラクチャおよびビジネス ニーズ
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso オンプレミス IT インフラストラクチャの基本構造と、大企業向け Microsoft 365 が企業のビジネス ニーズをどのように満たすかを理解します。
ms.openlocfilehash: 5dc47898aa0499bc4b62d22d37689d872116a9e7
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65101361"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contoso の IT インフラストラクチャおよびビジネス ニーズ

Contoso は、オンプレミスの集中型 IT インフラストラクチャから、クラウド ベースの個人生産性ワークロードとアプリケーションを組み込んだクラウドを含むセットアップに移行しています。

## <a name="existing-contoso-it-infrastructure"></a>Contoso の既存の IT インフラストラクチャ

Contoso 社では、ほとんど集中管理されたオンプレミスの IT インフラストラクチャを使用しており、アプリケーション データセンターはパリ本社に位置します。

これは、アプリケーション データセンター、DMZ、およびインターネットを備えた本社オフィスです。

![Contoso 社の既存の IT インフラストラクチャ。](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

オンプレミス アプリケーション データセンターのホストは次のとおりです: 

- SQL Server や他の Linux データベースを使用するカスタムの基幹業務アプリケーション。
- 従来の SharePoint サーバーのセット。
- ファイル記憶域用の組織およびチームレベルのサーバー。

さらに、各地域のハブ オフィスは、同様のアプリケーション セットを持つサーバー セットをサポートしています。 これらのサーバーは、地域の IT 部門が管理します。

こうした地理的に離れた複数のデータセンターのアプリケーションとデータに対する検索性については引き続き課題です。

Contoso 本社の境界ネットワークでは、サーバーのさまざまなセットが次のことを実現します。

- 顧客が製品、部品、備品、サービスを発注できる Contoso 社のパブリック Web サイトのホスティング。
- パートナーの通信およびコラボレーションのための Contoso 社のパートナー エクストラネットのホスティング。
- パリ本社の従業員のための Contoso 社イントラネットおよび Web プロキシへの仮想プライベート ネットワーク (VPN) ベースのリモート アクセス。

## <a name="contoso-business-needs"></a>Contoso 社のビジネス ニーズ

Contoso 社のビジネス ニーズは、次の 5 つの主なカテゴリに分類されます。

**生産性**

- グループ作業を容易にする

  メールとファイル共有ベースのコラボレーションを、ドキュメントのリアルタイム変更、より簡単なオンライン会議、およびキャプチャされた会話スレッドを可能にするオンライン モデルに置き換えます。
- リモート ワーカーとモバイル ワーカーの生産性を向上させる

  多くの従業員が自宅や現場で働いているため、ボトルネックとなっている VPN ソリューションを、クラウド内の Contoso 社のデータとリソースへの効率的なアクセスに変更します。
- 独創性と革新性を向上させる

  手描き入力や 3D の視覚エフェクトなど最新のビジュアル学習とアイデア開発の方法を活用できます。

**セキュリティ**

- ID およびアクセス管理

  多要素認証および他の形式の認証を適用し、ユーザーおよび管理者アカウントの資格情報を保護します。

- 脅威保護

  メールおよびオペレーティング システム ベースのマルウェアなど、外部のセキュリティの脅威から保護します。

- 情報保護

  顧客データ、設計および製造仕様、従業員情報などの重要なデジタル資産へのアクセスを制限し、暗号化します。

- セキュリティ管理

  セキュリティ体制を監視し、脅威をリアル タイムで検出して対応します。

**リモート/モバイル アクセスおよびビジネス パートナー**

- リモートおよびモバイルワーカーのセキュリティを向上させる

  持ち込みデバイス (BYOD) と会社所有のデバイスの管理を実装し、確実にアクセスをセキュリティで保護し、アプリケーションを正しく動作させ、企業データを保護できるようにします。

- 従業員のリモート アクセス インフラストラクチャを縮小する

  よくアクセスされているリソースをクラウドに移動することで、保守作業とサポートのコストを削減し、リモート アクセス ソリューションのパフォーマンスを向上させます。

- 企業間 (B2B) のトランザクションにおける接続性を向上し、オーバーヘッドを削減する

  老朽化が進み、維持にコストがかかるパートナー エクストラネットを、フェデレーション認証を使用するクラウドベースのソリューションに切り替えます。

**コンプライアンス**

- 地域の規制要件に準拠する

  データ ストレージ、暗号化、データ プライバシー、および欧州連合の一般データ保護規則 (GDPR) などの個人データ規制に関する業界および地域の規制への準拠を確認します。

**管理**

- クライアント PC とデバイスで実行されているソフトウェアを管理するために、IT オーバーヘッドを削減します。

  組織全体で Windows オペレーティング システムと Microsoft 365 Apps for enterprise の更新プログラムのインストールを自動化します。

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Contoso 社のビジネス ニーズを大企業向け Microsoft 365 にマッピングする

Contoso 社の IT 部門は展開に先立ち、Microsoft 365 E5 の機能への以下のビジネス ニーズのマッピングを決定しました。


| カテゴリ | ビジネス ニーズ | 大企業向け Microsoft 365 の製品または機能 |
|:-------|:-----|:-----|
| 生産性 |  |  |
|  | グループ作業を容易にする | Microsoft Teams、SharePoint、OneDrive |
|  | リモート ワーカーとモバイル ワーカーの生産性を向上させる | Microsoft 365 のワークロードとクラウドベースのデータ |
|  | 独創性と革新性を向上させる | Windows Ink、職場の Cortana、PowerPoint |
| セキュリティ |  |  |
|  | ID およびアクセス管理 | Azure AD 多要素認証 (MFA) および Azure AD Privileged Identity Management (PIM) 付きの専用のグローバル管理者アカウント <br> すべてのユーザー アカウントの MFA <br> 条件付きアクセス <br> セキュリティ閲覧者 <br> Windows Hello <br> Windows Credential Guard |
|  | 脅威保護 | Advanced Threat Analytics <br> Windows Defender <br> Defender for Office 365 <br> Microsoft Defender for Office 365 <br> Microsoft 365 脅威の調査および対応 <br> |
|  | 情報保護 | Azure Information Protection <br> データ損失防止 (DLP) <br> Windows 情報保護 (WIP) <br> Microsoft Defender for Cloud Apps <br> Microsoft Intune |
|  | セキュリティ管理 | Microsoft Defender for Cloud  <br> Windows Defender セキュリティ センター |
| リモート/モバイル アクセスおよびビジネス パートナー |  |  |
|  | リモート ワーカーとモバイル ワーカーのセキュリティを強化する | Microsoft Intune |
|  | 従業員のリモート アクセス インフラストラクチャを縮小する | Microsoft 365 のワークロードとクラウドベースのデータ |
|  | B2B のトランザクションにおける接続性を向上させ、オーバーヘッドを削減する | フェデレーション認証とクラウドベースのリソース |
| コンプライアンス |  |  |
|  | 地域の規制要件に準拠する | Microsoft 365 の GDPR 機能 |
| 管理 |  |  |
|  | クライアントの更新プログラムをインストールするため、IT オーバーヘッドを削減する | Windows 10 Enterprise の更新プログラム <br> Microsoft 365 Apps for enterprise の更新プログラム |
||||

## <a name="next-step"></a>次の手順

Contoso 社の[オンプレミス ネットワーク](contoso-networking.md)と、Microsoft 365 のクラウドベースのリソースへのアクセスと待ち時間を最適化した方法について確認します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
