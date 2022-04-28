---
title: Azure Active DirectoryでのMicrosoft 365分離とAccess Control
ms.author: robmazz
author: robmazz
manager: scotv
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: この記事では、分離とAccess Controlのしくみを説明し、複数のテナントのデータをAzure Active Directory内で相互に分離します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 409528847d04a55926138e49128f018b349da0a3
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093879"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Azure Active DirectoryでのMicrosoft 365分離とAccess Control

Azure Active Directory (Azure AD) は、論理的なデータ分離を通じて、安全性の高い方法で複数のテナントをホストするように設計されました。 Azure ADへのアクセスは、承認レイヤーによってゲートされます。 Azure ADは、テナント コンテナーをセキュリティ境界として使用して顧客を分離し、共同テナントがコンテンツにアクセスしたり侵害したりできないように、顧客のコンテンツを保護します。 Azure ADの承認レイヤーによって、次の 3 つのチェックが実行されます。

- プリンシパルは、Azure AD テナントへのアクセスが有効になっていますか?
- プリンシパルは、このテナント内のデータへのアクセスが有効になっていますか?
- このテナントのプリンシパルのロールは、要求されたデータ アクセスの種類に対して承認されていますか?

アプリケーション、ユーザー、サーバー、またはサービスは、適切な認証とトークンまたは証明書なしでAzure ADにアクセスできません。 要求に適切な資格情報が添付されていない場合、要求は拒否されます。

実質的には、Azure ADは、各テナントを独自の保護されたコンテナー内でホストし、テナントが単独で所有および管理するコンテナーとの間でポリシーとアクセス許可を持ちます。
 
![Azure コンテナー。](../media/office-365-isolation-azure-container.png)

テナント コンテナーの概念は、ポータルから永続ストレージまで、すべてのレイヤーのディレクトリ サービスに深く根付きます。 複数のAzure ADテナント メタデータが同じ物理ディスクに格納されている場合でも、コンテナー間には、ディレクトリ サービスによって定義されたもの以外の関係はなく、テナント管理者によって指示されます。 最初に承認レイヤーを経由せずに、要求しているアプリケーションまたはサービスからAzure ADストレージに直接接続することはできません。

次の例では、Contoso と Fabrikam の両方が個別の専用コンテナーを持ち、それらのコンテナーがサーバーやストレージなどの同じ基盤インフラストラクチャの一部を共有している場合でも、相互に分離され、承認とアクセス制御のレイヤーによってゲートされます。
 
![Azure 専用コンテナー。](../media/office-365-isolation-azure-dedicated-containers.png)

さらに、Azure AD内から実行できるアプリケーション コンポーネントはなく、あるテナントが別のテナントの整合性を強制的に侵害したり、別のテナントの暗号化キーにアクセスしたり、サーバーから生データを読み取ったりすることはできません。

既定では、Azure ADは、他のテナントの ID によって発行されたすべての操作を禁止します。 各テナントは、要求ベースのアクセス制御を通じてAzure AD内で論理的に分離されます。 ディレクトリ データの読み取りと書き込みのスコープはテナント コンテナーに適用され、内部抽象化レイヤーとロールベースのアクセス制御 (RBAC) レイヤーによってゲートされます。これにより、テナントがセキュリティ境界として強制されます。 すべてのディレクトリ データ アクセス要求は、これらのレイヤーによって処理され、Microsoft 365内のすべてのアクセス要求は、上記のロジックによってポリシーが適用されます。

Azure ADには、北米、米国政府、欧州連合、ドイツ、World Wide パーティションがあります。 テナントは 1 つのパーティションに存在し、パーティションには複数のテナントを含めることができます。 パーティション情報は、ユーザーから抽象化されます。 特定のパーティション (その中のすべてのテナントを含む) は、複数のデータセンターにレプリケートされます。 テナントのパーティションは、テナントのプロパティ (国コードなど) に基づいて選択されます。 各パーティション内のシークレットやその他の機密情報は、専用キーで暗号化されます。 キーは、新しいパーティションが作成されたときに自動的に生成されます。

Azure ADシステム機能は、各ユーザー セッションに固有のインスタンスです。 さらに、Azure ADでは、暗号化テクノロジを使用して、共有システム リソースをネットワーク レベルで分離して、情報の不正な転送や意図しない転送を防ぎます。
