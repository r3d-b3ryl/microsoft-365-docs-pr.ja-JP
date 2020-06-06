---
title: Microsoft 365 でリモート ワーカーを支援する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 05/27/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: ワーカーがいつでもどこからでもリモートで作業できるようにするセキュリティとサービスのインフラストラクチャを構成します。
ms.openlocfilehash: ce287cdf5bcbd0283252b08c035dc954044a9c0e
ms.sourcegitcommit: 416a4b87bfd7e5aff80194b59b2776f054aa8eb5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44534962"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Microsoft 365 でリモート ワーカーを支援する

組織のオンプレミスおよびクラウドベースの情報、ツール、リソースに、ワーカーが自宅から安全にアクセスできるようにすることが必要になる場合があります。 多くの組織にとって、ワーカーがシームレスかつ安全にオフィスから離れて仕事ができるようにすることは、以下のために重要です。

- オフィス スペースの節約。
- 配置転換を望まないワーカーを雇用し、維持する。
- ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。

リモート作業 (テレワーキングとも呼ばれる) は、次のような範囲に及ぶ可能性があります。

- 会議やクライアント会議のために時々オフィスを離れるワーカー。
- リモートでフルタイムで働く一部のワーカー。
- オフィスがなく、すべてのワーカーがリモートで作業をする完全なリモートの組織。

たとえば COVID-19 危機への対応として、リモート ワーカーをサポートするために、Microsoft 365 Enterprise の機能を組み合わせることで、次のような高度な共同作業が可能になります。

- オンライン会議およびチャット セッション。
- グローバルなアクセシビリティとリアルタイムのコラボレーションを実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。
- 作業を分割して完了するための共有タスクとワークフロー。

セキュリティを強化するために、Microsoft 365 には以下が含まれます。

- 認証要件の適用、高リスクのサインインの検出と応答、選択したアプリと非準拠デバイスのブロック。
- クラウド内の暗号化された接続とデジタル資産。
- ファイルに対して誰が何を実行できるかを定義する権限。
- Windows 10 デバイスを保護する包括的なセキュリティ機能。

これらのリモート ワーカーの基準を満たすには、次の Microsoft 365 機能を使用します。

- ユーザー ID とサインイン セキュリティ
  - 多要素認証 (MFA) を使用する Azure Active Directory (Azure AD) ユーザー アカウント
  - 危険なサインインに MFA を要求する条件付きアクセス ポリシー (Microsoft 365 E5)
- コラボレーション プラットフォーム
  - リモート ワーカーがオンライン ビデオベースの会議にスケジュールおよび参加し、同時に同じドキュメントで作業できるようにする Microsoft Teams、SharePoint、および OneDrive
- リソースへのアクセスを保護する
  - Teams、SharePoint サイト、および OneDrive のグループとアクセス許可により、認証および許可されたユーザーのみがアクセス可能
- 漏洩ファイルの保護
  - 暗号化のための機密ラベルとファイルとともに移動するアクセス許可
- Microsoft Intune によるデバイス管理とセキュリティ
  - 管理対象デバイスの登録
  - 個人用デバイスのアプリ設定
  - デバイスとアプリのポリシー
- デバイス用の生産性アプリ
  - Teams、Exchange、SharePoint、OneDrive とのコラボレーション エクスペリエンスのための Microsoft 365 Apps (Word、PowerPoint、Excel)  
- Windows 10 Enterprise
  - サイバー攻撃から保護し、データ漏洩を防止する包括的なセキュリティ機能の組み込みスイート
- オンプレミス アプリやサービスへのアクセス
  - 仮想プライベート ネットワーク (VPN) 接続、Azure AD アプリケーション プロキシ、Azure ポイント対サイト VPN

次の手順を実行することにより、組織のサーバー、データ、クラウド サービスへのアクセスをセキュリティで保護して最適化し、従業員の生産性を最大限に高めることができます。

1. [MFA を使用してリモート ワーカーのサインイン セキュリティを強化する](empower-people-to-work-remotely-secure-sign-in.md)
2. [オンプレミスのアプリとサービスへのリモート アクセスを提供する](empower-people-to-work-remotely-remote-access.md)
3. [デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する](empower-people-to-work-remotely-manage-endpoints.md)
4. [リモート ワーカー向けの生産性向上アプリとサービスを展開する](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [コミュニケーション会場を作成する](empower-people-to-work-remotely-communication-venues.md)
6. [リモート ワーカーをトレーニングし、使用状況のフィードバックに対処する](empower-people-to-work-remotely-train-monitor-usage.md)

![Microsoft 365 でリモート ワーカーを支援するための手順](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

リモート ワーカーのサポートに関する Microsoft の最新情報については、「[Enabling remote work Tech Community site (リモート ワークを可能にする技術コミュニティ サイト)](https://resources.techcommunity.microsoft.com/enabling-remote-work/)」を参照してください。
