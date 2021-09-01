---
title: Microsoft 365 でのアプリ ガバナンス
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Microsoft アプリ ガバナンス機能を実装し、アプリを管理します。
ms.openlocfilehash: f89214a71bc82ac7271ba3fd010258e63d39ef8a
ms.sourcegitcommit: 6a73f0f0c0360fc015d9c0d0af26fb6926d9477d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58744991"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Microsoft Cloud App Security へのアプリ ガバナンス アドオン (プレビュー版)

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

> [!NOTE]
> アプリ ガバナンスにサインアップするには、「[アプリ ガバナンスの開始 (プレビュー)](app-governance-get-started.md)」を参照してください。

サイバー攻撃は、オンプレミスやクラウドのインフラに展開しているアプリケーションを悪用する方法がますます巧妙になっており、特権の昇格、横方向の移動、データの流出の開始点となっています。 潜在的なリスクを理解し、この種の攻撃を阻止するためには、組織のアプリ コンプライアンス姿勢を明確に可視化し、アプリが異常な動作を示した場合には迅速に特定し、これらの動作が環境、データ、ユーザーにリスクとなる場合には対応する必要があります。

Microsoft Cloud App Security のアドオン機能であるアプリ ガバナンスは、Microsoft Graph API 経由で Microsoft 365 のデータにアクセスする OAuth 対応アプリ向けに設計されたセキュリティおよびポリシー管理機能です。 アプリ ガバナンスは、実用的な分析情報と自動化されたポリシー アラートおよびアクションを通して、これらのアプリとそのユーザーが Microsoft 365 に保存されている機密データにアクセスし、使用し、共有する方法について、完全な可視性、修復、およびガバナンスを提供します。

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

アプリ ガバナンスは、以下のように包括的に提供されます。

- **分析情報**: テナント内の Microsoft 365 プラットフォーム向けのすべてのサードパーティ製アプリを 1 つのダッシュボードに表示します。 すべてのアプリの状態やアラート アクティビティを確認し、それらに反応したり対応したりすることができます。
- **ガヴァナンス**: アプリやユーザーのパターンや行動に対するプロアクティブまたはリアクティブなポリシーを作成し、準拠していないアプリや悪意のあるアプリの使用からユーザーを保護し、リスクのあるアプリのデータへのアクセスを制限します。
- **検出**: アプリ アクティビティに異常が発生した場合や、準拠していないアプリ、悪意のあるアプリ、リスクのあるアプリが使用された場合に警告や通知が行われます。
- **修復**: 自動修復機能に加えて、アプリケーションの異常なアクティビティの検出に対応するために、修復制御をタイムリーに使用します。

アプリ ガバナンスは、Microsoft 365 アプリ エコシステムに不可欠なプラットフォームベースのソリューションです。 アプリ ガバナンスは、Azure Active Directory (Azure AD) に登録され、Microsoft Graph API 経由でデータにアクセスする OAuth 対応アプリを監督し、管理します。 アプリ ガバナンスでは、アプリケーションの動作を制御することで、IT インフラストラクチャのセキュリティとコンプライアンスの態勢を強化することができます。

## <a name="a-first-glimpse-at-app-governance"></a>アプリ ガバナンスを一目見る

アプリ ガバナンスのダッシュボードを表示するには、[https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance) にアクセスします。 アプリ ガバナンス データを表示するには、サインイン アカウントに[管理者の役割](app-governance-get-started.md#administrator-roles)のいずれかが必要であることに注意してください。

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>Azure AD と Microsoft Cloud App Security を使用したアプリ ガバナンスの統合

App ガバナンス、Azure AD、Microsoft Cloud App Security は、以下のようなさまざまなデータセットを収集して提供します。

- アプリ ガバナンスは、API レベルでのアプリのアクティビティに関する詳細情報を提供します。
- Azure AD は、アプリの基礎となるメタデータと、アプリへのサインインに関する詳細な情報を提供します。
- Microsoft Cloud App Security は、アプリのリスク情報を提供します。

アプリ ガバナンス、Azure AD、Microsoft Cloud App Security で情報を共有することで、集約された情報を 1 つのポータルに表示し、詳細情報を得るために別のポータルに簡単にリンクすることができます。次に、いくつかの例を示します:

- アプリ ガバナンスにおけるアプリのサインイン情報:

  アプリ ガバナンス ポータルでは、各アプリの集約されたサインイン アクティビティを表示でき、サインイン イベントの詳細については Azure Active Directory 管理センターにリンクすることができます。

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Microsoft Cloud App Security ポータルの API 使用情報:

  Microsoft Cloud App Security ポータルからは、API の使用レベルや集計データの転送を表示することができ、詳細はアプリ ガバナンス ポータルにリンクされます。

統合の概要は次のとおりです。

![Azure AD と Microsoft Cloud App Security を使用したアプリ ガバナンスの統合。](..\media\manage-app-protection-governance\mapg-integration.png)

アプリ ガバナンスはそのアラートを Microsoft Cloud App Security と Microsoft 365 Defender に送信し、Microsoft Cloud App Security からのアラートを受信することで、アプリベースのセキュリティ インシデントをより詳細に分析することができます。
- アプリ ガバナンス アラートは、[検出ソース] フィールドが "MAPG" に設定されたアラートとして Microsoft 365 Defender アラート リストに表示されます
- アプリ ガバナンス アラートは、[ポリシー] フィールドがいずれかに設定されたアラートとして MCAS アラート リストに表示されます
  - Microsoft 365 OAuth アプリ ガバナンス
  - Microsoft 365 OAuth フィッシング検出
  - Microsoft 365 OAuth アプリの評価
- MCAS アラートは、[ソース] が MCAS に設定されたアラートとしてアプリ ガバナンス アラート リストに表示されます

> [!NOTE]
> アラートの状態は現在、アプリ ガバナンスと Microsoft Cloud App Security の間で同期されていません。
