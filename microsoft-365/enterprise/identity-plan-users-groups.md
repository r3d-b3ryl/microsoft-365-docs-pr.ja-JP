---
title: '手順 1: ユーザーおよびグループを計画する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 組織に最適なユーザーとグループのセットを計画します。
ms.openlocfilehash: c74ff672ce84a5609c11eb4fa7a0405d350349ab
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553296"
---
# <a name="step-1-plan-for-users-and-groups"></a>手順 1: ユーザーおよびグループを計画する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、正しい構成でセキュリティ機能とユーザー、グループ、およびグループ メンバーシップを組み合わせた ID インフラストラクチャを作成します。これにより、次の操作が可能になります。

- 環境内のリソースにアクセスできるユーザーを制御する。
- ID の強力な保証 (ユーザーは、そのユーザーが宣言したとおりである) と安全なデバイスからのアクセスを実現するコントロールにより、アクセスを保護する。
- 適切なアクセス許可を使用して環境内のリソースをプロビジョニングし、データの損傷や漏洩が発生する可能性を低減させる。 
- 環境で異常なユーザーの行動を監視し、自動的に処置を実行する。

## <a name="plan-your-primary-identity-provider"></a>プライマリ ID プロバイダーを計画する

ID インフラストラクチャを作成するには、プライマリ ID プロバイダーを指定します。このサービスは、ユーザー アカウントとその属性、グループとメンバーシップを保存し、それらの継続的な管理をサポートします。

組織が Microsoft 365 Enterprise を導入する場合、プライマリ ID プロバイダーは次のいずれかです。

- **Active Directory Domain Services (AD DS)**: Windows Server を実行しているコンピューターでホストされているイントラネット ID プロバイダーです。 これは通常、既存のオンプレミス ID プロバイダーを持つ組織で使用されます。
- **Azure Active Directory (Azure AD)**: 環境の管理および保護のためのさまざまな機能を提供するクラウドベースの Identity as a Service (IDaaS) です。 これは通常、既存のオンプレミス インフラストラクチャを持たない組織で使用されます。

組織に既存のオンプレミス ID プロバイダーがある場合、AD DS のユーザー アカウントとグループを Azure AD と同期し、Microsoft 365 Enterprise のクラウドベース サービスによりシームレスにアクセスできるようにします。 また、Azure AD を使用して、Microsoft クラウドにのみ存在するグループを作成および管理することもできます。

Azure AD でユーザーとグループを作成した後には、次の操作を実行できます。

- すべてのクラウド アプリケーションのすべての Azure AD アカウントを管理する。 
- 同じコントロールのセットを使用して、環境全体でアプリケーションへのアクセスを保護する。
- 外部パートナーと共同作業を行う。
- アカウントの異常な動作 (不審なサインイン試行など) を監視し、自動的に対処する。

次の 2 つのセクションで説明する手順に従い、ユーザー アカウントおよびグループを計画および導入します。

## <a name="categorize-your-users"></a>ユーザーを分類する
組織内のユーザーは、さまざまな方法で分類できます。たとえば、永続的なステータスを持つ正社員、一時的なステータスを持つベンダー、契約社員、パートナーなどです。また、ユーザー アカウントを持たないものの、コミュニケーションやコラボレーションに対応するため特定のサービスとリソースへのアクセスを許可する必要がある外部ユーザーなどもあります。次に例を示します。

- テナント アカウントは、組織内でクラウド サービスのライセンスを付与したユーザーを表します。
- B2B (Business to Busines) アカウントは、コラボレーションへの参加のために招待された組織外部のユーザーを表します。

組織のユーザーの既存の種類を調べます。どのようにグループ化していますか。たとえば、組織の上位の職種または目的によりユーザーをグループ化できます。

また、一部のクラウド サービスを、ユーザー アカウントを持たない組織外のユーザーと共有できます。この場合、このような外部ユーザーのグループも指定する必要があります。

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a>AD DS と Azure AD グループの計画

Azure AD では、クラウド環境の管理を簡素化するさまざまな目的のためにグループを使用できます。たとえば、Azure AD グループでは次の操作を実行できます。

- グループベースのライセンスを使用して、ユーザー アカウントが Azure AD に追加された時点または AD DS から同期された時点で、Office 365 と Enterprise Mobility + Security (EMS) のライセンスをアカウントに自動的に割り当てる。 
- ユーザー アカウントの属性 (部門など) に基づいて、ユーザー アカウントを特定のグループに動的に追加する。  
- Software as a Service (SaaS) アプリケーションのユーザーを自動的にプロビジョニングし、多要素認証やその他の条件付きアクセス ルールでこれらのアプリケーションへのアクセスを保護する。
- SharePoint Online チーム サイトのアクセス許可とアクセス レベルをプロビジョニングする。Azure AD グループを Azure Information Protection スコープ ポリシーと組み合わせて使用し、暗号化とアクセス許可でファイルを保護できる。 

## <a name="results"></a>結果

この手順の完了後の成果物は次のとおりです。

- 組織内の従業員、ベンダー、契約社員、組織のために働くまたは組織と協働する外部パートナーに対応する、Azure AD のユーザー アカウントのリスト。
- Azure AD のグループとそのメンバーシップのセット。これは、Microsoft クラウド サービスのセキュリティ設定の自動ライセンス プロビジョニングのためのユーザー アカウントおよびその他のグループの論理セットを反映しています。

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-user-groups)を確認できます。

Azure AD のユーザーとグループが作成されると、ライセンスを割り当てて、Exchange Online の使用を開始できます。 Exchange Online をユーザーにロールアウトするには、[Microsoft 365 Enterprise 用 Exchange Online を展開する](exchangeonline-workload.md)を参照してください。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [特権 ID をセキュリティで保護する](identity-designate-protect-admin-accounts.md) |

