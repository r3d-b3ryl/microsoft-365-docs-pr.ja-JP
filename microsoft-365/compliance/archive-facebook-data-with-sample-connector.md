---
title: コネクタをセットアップしてFacebook のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: このページでコネクタを&して、Facebook Business Microsoft 365 コンプライアンス センターページから&にアーカイブ データをインポートする方法についてMicrosoft 365。
ms.openlocfilehash: 766f7858c6e5117190712d3daad68b2b7b4e37c2
ms.sourcegitcommit: 4582873483bd52bc790bf75b838cc505dc4bbeb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58502653"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Facebook データをアーカイブするコネクタをセットアップする (プレビュー)

ページのコネクタを使用Microsoft 365 コンプライアンス センター、Facebook Business ページからデータをインポートおよびアーカイブして、Microsoft 365。 コネクタを設定して構成すると、(スケジュールに基づいて) Facebook Business ページに接続し、Facebook アイテムのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

Facebook データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Facebook データに適用できます。 たとえば、メールボックスが訴訟ホールドに置かれたり、アイテム保持ポリシーに割り当てられたりすると、Facebook データは保持されます。 コンテンツ検索を使用してサード パーティのデータを検索したり、Facebook データが保管担当者に保存されているメールボックスを特定のケースに関連付Advanced eDiscoveryできます。 コネクタを使用して Facebook データをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Facebook Business ページのコネクタを設定するための前提条件

組織の Facebook Business ページからデータをインポートおよびアーカイブするために、Microsoft 365 コンプライアンス センターコネクタをセットアップして構成する前に、次の前提条件を満たします。 

- 組織のビジネス ページ用の Facebook アカウントが必要です (コネクタをセットアップする場合は、このアカウントにサインインする必要があります)。 現時点では、Facebook Business ページからのみデータをアーカイブできます。個々の Facebook プロファイルからデータをアーカイブできない。

- 組織に有効な Azure サブスクリプションが必要です。 既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。

    - [無料の 1 年間 Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free)

    - [Pay-As-Go Azure サブスクリプションにサインアップする](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > サブスクリプション[にAzure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md)されている無料のサブスクリプションは、Microsoft 365のコネクタをサポートMicrosoft 365 コンプライアンス センター。

- Facebook Business ページのコネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 件を超える Facebook Business アイテムがある場合、それらのアイテムはいずれも 1 日にインポートMicrosoft 365。

- (手順 5 で) Microsoft 365 コンプライアンス センターでカスタム コネクタを設定するユーザーには、メールボックスのインポート エクスポートの役割が割り当てられている必要Exchange Online。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: アプリをアプリで作成Azure Active Directory

最初の手順は、新しいアプリをアプリ (AAD) Azure Active Directory登録します。 このアプリは、Facebook コネクタの手順 4 と手順 5 で実装する Web アプリ リソースに対応します。 

手順については、「アプリを作成する[」](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)を参照Azure Active Directory。

この手順が完了すると (前の手順を使用して)、次の情報をテキスト ファイルに保存します。 これらの値は、展開プロセスの後の手順で使用されます。

- AAD アプリケーション ID

- AAD アプリケーション シークレット

- テナント ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: コネクタ Web サービスを Azure アカウントGitHubから展開する

次の手順では、Facebook API を使用して Facebook アカウントに接続し、データを抽出する Facebook Business ページ コネクタ アプリのソース コードを展開し、そのソース コードを Microsoft 365 にインポートします。 組織に展開する Facebook コネクタは、Facebook Business ページからこの手順で作成Azure Storage場所にアイテムをアップロードします。 Microsoft 365 コンプライアンス センター (手順 5) で Facebook ビジネス ページ コネクタを作成すると、インポート サービスは、Azure Storage の場所から Microsoft 365 組織内のメールボックスに Facebook ビジネス ページ データをコピーします。 [前提条件] セクションで[説明したように](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)、有効な Azure サブスクリプションを使用して、アカウントを作成Azure Storageがあります。

詳細な手順については、「コネクタ Web サービスを Azure アカウントに展開する」を参照GitHub[を参照してください](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

この手順を完了する手順では、次の情報を提供します。

- APISecretKey: この手順の完了時に、このシークレットを作成します。 手順 5 で使用します。

- TenantId: 手順 1 Microsoft 365で Facebook コネクタ アプリを作成した後にコピーした組織Azure Active Directory ID。

この手順を完了した後は、必ず Azure アプリ サービスの URL (など) をコピーしてください https://fbconnector.azurewebsites.net) 。 この URL を使用して、手順 3、手順 4、および手順 5) を完了する必要があります。

## <a name="step-3-register-the-web-app-on-facebook"></a>手順 3: Facebook に Web アプリを登録する

次の手順では、Facebook で新しいアプリを作成して構成します。 手順 5 で作成した Facebook ビジネス ページ コネクタは、Facebook Web アプリを使用して Facebook API と対話し、組織の Facebook Business ページからデータを取得します。

手順については、「Facebook アプリの登録 [」を参照してください](deploy-facebook-connector.md#step-3-register-the-facebook-app)。

この手順の完了時 (手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、手順 4 で Facebook コネクタ アプリを構成するために使用されます。

- Facebook アプリケーション ID

- Facebook アプリケーション シークレット

- Facebook Webhooks のトークンの確認

## <a name="step-4-configure-the-facebook-connector-app"></a>手順 4: Facebook コネクタ アプリを構成する

次の手順では、手順 1 で Azure Web アプリ リソースを作成した際にアップロードした Facebook コネクタ アプリに構成設定を追加します。 これを行うには、コネクタ アプリのホーム ページに移動して構成します。

詳細な手順については [、「Configure the Facebook Connector app」を参照してください](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。

この手順の完了時 (手順に従って)、次の情報 (前の手順を完了した後にテキスト ファイルにコピーした情報) を指定します。

- Facebook アプリケーション ID (手順 3 で取得)

- Facebook アプリケーション シークレット (手順 3 で取得)

- Facebook Webhooks verify token (手順 3 で取得)

- Azure Active Directory ID (手順 1 で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Facebook Business ページ コネクタをセットアップするには、Microsoft 365 コンプライアンス センター

最後の手順では、Facebook Business ページからデータをインポートするコネクタを、Microsoft 365 コンプライアンス センター で指定したメールボックスにインポートするコネクタをMicrosoft 365。 この手順を完了すると、Microsoft 365インポート サービスが Facebook Business ページからデータのインポートを開始Microsoft 365。

手順については、「手順[5:](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)Facebook コネクタをセットアップする」を参照Microsoft 365 コンプライアンス センター。 

この手順の完了時 (手順の手順に従って) は、次の情報 (手順の完了後にテキスト ファイルにコピーした情報) を提供します。

- AAD アプリケーション ID (手順 1 で取得)

- Azure アプリ サービスの URL (手順 1 で取得されます。たとえば、 https://fbconnector.azurewebsites.net)

- APISecretKey (手順 2 で作成した)