---
title: Contoso 社の極秘プロジェクトのチーム
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: Contoso 社がトップ機密プロジェクトの高度な規制データに対してチームを使用して、新しいスイートの製品とサービスを開発する方法について説明します。'
ms.openlocfilehash: 794fb5cfb6f3011724d37a6a3c42c39dacacc270
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597074"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso 社の極秘プロジェクトのチーム

上級管理職がオフサイトになると、Contoso 社の CEO は、今後5年間で Contoso 社の利益を2倍にすることができる新しいスイートの製品とサービスの開発を命じました。 ビジネス、エンジニアリング、マーケットプランを開発する最上位のプロジェクトは、 **Project 2x**という名前で、会社全体にわたる主なスタッフは recruited でした。 

研究開発のタイムラインは厳しいものでした。つまり、共同作業を効率的に行い、セキュリティで保護された会議、継続的な会話、ファイルストレージを提供する必要がありました。

プロジェクト2X の結果として得られる成果物は、ビジネスプラン、製品とエンジニアリングの仕様、およびマーケティング資料とスケジュールが、Word、Excel、および PowerPoint のファイルの形式で表示されます。 

機密情報のため、これらのファイルへのアクセスは次のようになりました。

- プロジェクト2チームメンバーに制限されます。
- データ損失防止 (DLP) ポリシーによって保護され、Project 2X チームメンバーがチーム外で共有できないようにします。
- ファイルが Contoso 外に配布された場合でも、Project 2X のチームメンバーにのみアクセスを許可するためのアクセス許可によって暗号化および保護されます。

Contoso IT スタッフは、Project 2X の[高度な規制データにチーム](secure-teams-highly-regulated-data-scenario.md)を使用して、これらの手順を実行していました。

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>手順 1: プライベートチームを作成し、基盤となる SharePoint サイトをロックした

チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が[推奨する sharepoint アクセスポリシー](sharepoint-file-access-policies.md)を構成しました。

次に Contoso IT 管理者は、Project 2X という名前の新しいプライベートチームを作成し、Project 2X スタッフのユーザーアカウントをメンバーとして追加しました。

次に、プロジェクト2X がサイトへのアクセスを共有したり、他のユーザーがサイトへのアクセスを要求できないようにするために、サイトの追加のアクセス許可の設定を構成しました。

構成の詳細については、「[高度な規制チームの SharePoint 設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)」を参照してください。

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>手順 2: DLP ポリシーと、保持ラベルの基礎となるサイトを構成します。 

最初に、Contoso 管理者は、Project 2X team の基礎となる SharePoint サイトの**ドキュメント**セクションに、既存の**非常に機密性の高い**Office 365 保持ラベルを適用しました。

次に、 **Project 2x**という新しい OFFICE 365 DLP ポリシーを作成しました。次のようになります。

- 非常に機密性の高い Office 365 保持ラベルを使用します。
- ユーザーが Contoso の外部のプロジェクト2X チーム内のファイルを共有しようとすると、ユーザーをブロックします。

構成の詳細については、「[保持ラベルおよび DLP を使用した teams でファイルを保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)する」を参照してください。

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a>手順 3: Project 2X チームの Office 365 機密ラベルを作成する

Contoso 管理者は、 **Project 2x**という名前の新しい Office 365 機密ラベルを作成しました。

- 暗号化が必要です。
- Project 2X Office 365 グループに対して共同編集権限を許可します。

プロジェクト2チームの最終的な構成を次に示します。

![プロジェクト2チームの最終的な構成](./media/contoso-team-for-highly-confidential-assets/final-config.png)
 
基になる Project 2X SharePoint サイトの [ドキュメント] セクションにあるファイルは、次の方法で保護されています。

- サイトのアクセス許可。これは、Project 2X Office 365 グループのメンバーにのみアクセスを許可します。
- 新しいファイルに自動的に割り当てられる、高機密保持ラベル。
- 高機密保持ラベルと、そのファイルを外部ユーザーと共有することをブロックする設定を使用する DLP ポリシー。
- プロジェクトがサイトから移動またはコピーされた場合に、ファイルと共に送信される、暗号化とアクセス許可を持つ2つのプロジェクトの機密ラベル。

ここでは、基本となる Project 2X サイトに保存されているファイルのうち、高度な規制保持ラベルと Project 2X 機密ラベルが割り当てられているファイルの例を示します。

![基になる Project 2X サイトに保存されているファイルの例](./media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>手順 4: トレーニングを受けた Project 2X チームメンバー

Contoso のセキュリティスタッフは、次の手順に従ってステップ実行する必須のコースで、Project 2X のチームメンバーをトレーニングしています。

- 新しい Project 2X teams にアクセスする方法、会議とチャットを使用する方法、およびチームファイルで共同作業する方法について説明します。
- チーム内で新しいファイルを作成し、ローカルに作成された新しいファイルをアップロードする方法について説明します。
- DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。
- Project 2X 機密ラベルを使用してファイルにラベルを付ける方法について説明します。
- プロジェクトの2つのラベルがチームを離れたときでもファイルを保護する方法についてのデモ。

最終的には、セキュリティで保護された環境で、Project 2X のチームメンバーがチャット、会議、およびファイルのセキュリティで保護された環境で共同作業を行うことができました。

いくつかのインスタンスでは、Project 2X のチームメンバーは、オフライン作業のために Project 2X ラベルで保護されたファイルをローカルドライブにダウンロードしていました。 ただし、資格情報を開くときに資格情報の入力を求められた後で、それらの間違いを認識して削除しました。

Teams のグループ作業環境と Microsoft 365 のセキュリティ機能により、project 2X の詳細はプロジェクトの期間中に機密情報として保持されていました。 Contoso 社はプランを発表し、新しい製品とサービスを顧客や投資家の成功および競合他社の chagrin に展開する過程にあります。

## <a name="next-step"></a>次の手順

[展開](deploy-microsoft-365-enterprise.md)組織内の Microsoft 365 Enterprise。

## <a name="see-also"></a>関連項目

[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
