---
title: アプリの脅威の検出と修復に関する詳細情報
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: アプリの脅威の検出と修復について説明します。
ms.openlocfilehash: 90cddc1ffc386a2f691b27e77765a42f46778c82
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171017"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>アプリの脅威の検出と修復に関する詳細情報

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft アプリ ガバナンスを使用すると、次の情報を確認できます:

- 悪意のあるアプリ アクティビティに対し組み込みのアプリ ガバナンス検出方法により生成された脅威アラート、および作成したアクティブなアプリ ポリシーによって生成されたポリシー ベースのアラートを簡単に監視します。 これらのアラートは、アプリ アクティビティの異常や、準拠していないアプリ、悪意のあるアプリ、リスクのあるアプリが使用されていることを示している可能性があります。  アラートのパターンを使用して、新しいアプリ ポリシーを作成したり、既存のポリシーの設定を変更して、より制限的なアクションを実行したりすることもできます。
- アラートを、調査後に手動で、またはアクティブなアプリ ポリシーのアクション設定を介して自動的に、簡単に修正できます。


>[!Note]
>Microsoft 365 リソースにアクセスするためのアクセス許可が付与されていない、Azure のみのアプリからの異常なアクティビティは、アプリ ガバナンスの検出とアラートには含まれません。
>

アプリ ガバナンス ページにアクセスできる[管理者の役割](app-governance-get-started.md#administrator-roles)を参照してください。


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>Azure Active Directory と Microsoft Cloud App Security を使用したアプリ ガバナンスの統合

アプリ ガバナンス、Azure Active Directory (Azure AD)、Microsoft Cloud App Security は、以下のようなさまざまなデータセットを収集して提供します。

- アプリ ガバナンスは、API レベルでのアプリのアクティビティに関する詳細情報を提供します。
- Azure AD は、アプリの基礎となるメタデータと、アプリへのサインインに関する詳細な情報を提供します。
- Microsoft Cloud App Security は、アプリのリスク情報を提供します。

アプリ ガバナンス、Azure AD、Microsoft Cloud App Security で情報を共有することで、集約された情報を 1 つのポータルに表示し、詳細情報を得るために別のポータルに簡単にリンクすることができます。次に、いくつかの例を示します:

- アプリ ガバナンスにおけるアプリのサインイン情報:

  アプリ ガバナンス ポータルでは、各アプリの集約されたサインイン アクティビティを表示でき、サインイン イベントの詳細については Azure Active Directory 管理センターにリンクすることができます。

- Microsoft Cloud App Security ポータルの API 使用情報: 

  Microsoft Cloud App Security ポータルからは、API の使用レベルや集計データの転送を表示することができ、詳細はアプリ ガバナンス ポータルにリンクされます。

統合の概要は次のとおりです。

![Azure AD と Microsoft Cloud App Security を使用したアプリ ガバナンスの統合。](..\media\manage-app-protection-governance\mapg-integration.png)

また、アプリ ガバナンスはそのアラートをシグナルとして Microsoft Cloud App Security と Microsoft 365 Defender に送信し、アプリベースのセキュリティ インシデントをより詳細に分析することができます。

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>次の手順

[アプリの脅威の検出と修復を開始します。](app-governance-detect-remediate-get-started.md)
