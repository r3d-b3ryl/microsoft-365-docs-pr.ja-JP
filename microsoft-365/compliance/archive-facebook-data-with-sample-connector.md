---
title: コネクタをセットアップしてFacebook のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 07/15/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Microsoft Purview コンプライアンス ポータルのコネクタを使用&設定して、Facebook Business ページから Microsoft 365 に&アーカイブ データをインポートする方法について説明します。
ms.openlocfilehash: 79238bbbdcea71cf83342894d3b61e8047f5897a
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822881"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Facebook データをアーカイブするコネクタを設定する (プレビュー)

Microsoft Purview コンプライアンス ポータルのコネクタを使用して、Facebook Business ページから Microsoft 365 にデータをインポートおよびアーカイブします。 コネクタを設定して構成すると、Facebook Business ページ (スケジュールに基づいて) に接続され、Facebook アイテムのコンテンツが電子メール メッセージ形式に変換され、Microsoft 365 のメールボックスにそれらのアイテムがインポートされます。

Facebook データがインポートされたら、訴訟ホールド、コンテンツ検索、In-Placeアーカイブ、監査、コミュニケーション コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft Purview 機能を Facebook データに適用できます。 たとえば、メールボックスを訴訟ホールドに置いたり、アイテム保持ポリシーに割り当てたりすると、Facebook データは保持されます。 コンテンツ検索を使用してサード パーティのデータを検索したり、Facebook データが保存されているメールボックスをMicrosoft Purview eDiscovery (Premium) ケースのカストディアンに関連付けることができます。 コネクタを使用して Microsoft 365 で Facebook データをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

プレビューに参加する場合は、dcfeedback@microsoft.com のチームにお問い合わせください。

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Facebook Business ページのコネクタを設定するための前提条件

コンプライアンス ポータルでコネクタを設定して構成し、組織の Facebook Business ページからデータをインポートおよびアーカイブする前に、次の前提条件を満たしてください。 

- 組織のビジネス ページには Facebook アカウントが必要です (コネクタを設定するときは、このアカウントにサインインする必要があります)。 現時点では、Facebook Business ページからのみデータをアーカイブできます。個々の Facebook プロファイルからデータをアーカイブすることはできません。

- 組織に有効な Azure サブスクリプションが必要です。 既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。

    - [無料の 1 年間の Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free)

    - [従量課金制 Azure サブスクリプションにサインアップする](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 [サブスクリプションに含まれる無料の Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) サブスクリプションは、コンプライアンス ポータルのコネクタをサポートしていません。

- Facebook Business ページのコネクタでは、1 日に合計 200,000 個のアイテムをインポートできます。 1 日に 200,000 件を超える Facebook Business アイテムがある場合、これらのアイテムは Microsoft 365 にインポートされません。

- コンプライアンス ポータルでカスタム コネクタを設定するユーザー (手順 5) には、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順では、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、Facebook コネクタの手順 4 と手順 5 で実装した Web アプリ リソースに対応します。

詳細な手順については、「 [Azure Active Directory でアプリを作成する」を](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)参照してください。

この手順が完了したら (前の手順を使用して)、次の情報をテキスト ファイルに保存します。 これらの値は、デプロイ プロセスの後の手順で使用されます。

- AAD アプリケーション ID

- AAD アプリケーション シークレット

- テナント ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: GitHub から Azure アカウントにコネクタ Web サービスをデプロイする

次の手順では、Facebook API を使用して Facebook アカウントに接続し、Microsoft 365 にインポートできるようにデータを抽出する Facebook Business ページ コネクタ アプリのソース コードをデプロイします。 組織にデプロイする Facebook コネクタは、Facebook Business ページから、この手順で作成された Azure Storage の場所にアイテムをアップロードします。 コンプライアンス ポータルで Facebook ビジネス ページ コネクタを作成すると (手順 5)、インポート サービスによって、Azure Storage の場所から Microsoft 365 組織内のメールボックスに Facebook ビジネス ページデータがコピーされます。 「 [前提条件」](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) セクションで説明したように、Azure Storage アカウントを作成するには、有効な Azure サブスクリプションが必要です。

詳細な手順については、「 [GitHub から Azure アカウントにコネクタ Web サービスをデプロイする」を参照してください](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

この手順を完了するための詳細な手順では、次の情報を指定します。

- APISecretKey: この手順の完了時に、このシークレットを作成します。 手順 5. で使用します。

- TenantId: 手順 1 で Azure Active Directory で Facebook コネクタ アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。

この手順を完了したら、必ず Azure アプリ サービスの URL (例: https://fbconnector.azurewebsites.net). 手順 3、手順 4、および手順 5) を完了するには、この URL を使用する必要があります。

## <a name="step-3-register-the-web-app-on-facebook"></a>手順 3: Facebook に Web アプリを登録する

次の手順では、Facebook で新しいアプリを作成して構成します。 手順 5 で作成した Facebook ビジネス ページ コネクタでは、Facebook Web アプリを使用して Facebook API と対話し、組織の Facebook Business ページからデータを取得します。

詳細な手順については、「 [Facebook アプリを登録する」を](deploy-facebook-connector.md#step-3-register-the-facebook-app)参照してください。

この手順が完了したら (手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、手順 4 で Facebook コネクタ アプリを構成するために使用されます。

- Facebook アプリケーション ID

- Facebook アプリケーション シークレット

- Facebook Webhook がトークンを確認する

## <a name="step-4-configure-the-facebook-connector-app"></a>手順 4: Facebook コネクタ アプリを構成する

次の手順では、手順 1 で Azure Web アプリ リソースを作成したときにアップロードした Facebook コネクタ アプリに構成設定を追加します。 これを行うには、コネクタ アプリのホーム ページに移動し、構成します。

詳細な手順については、「 [Facebook コネクタ アプリの構成」を](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)参照してください。

この手順の完了時に (詳細な手順に従って) 次の情報を指定します (前の手順を完了した後にテキスト ファイルにコピーした情報)。

- Facebook アプリケーション ID (手順 3 で取得)

- Facebook アプリケーション シークレット (手順 3 で取得)

- Facebook Webhook によってトークンが確認されます (手順 3 で取得)

- Azure Active Directory アプリケーション ID (手順 1 で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-compliance-portal"></a>手順 5: コンプライアンス ポータルで Facebook Business ページ コネクタを設定する

最後の手順では、コンプライアンス ポータルでコネクタを設定し、Facebook Business ページから Microsoft 365 の指定されたメールボックスにデータをインポートします。 この手順を完了すると、Microsoft 365 Import サービスによって、Facebook Business ページから Microsoft 365 へのデータのインポートが開始されます。

詳細な手順については、「 [手順 5: コンプライアンス ポータルで Facebook コネクタを設定する」を](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-compliance-portal)参照してください。

この手順の完了時に (手順に従って) 次の情報を指定します (手順の完了後にテキスト ファイルにコピーした情報)。

- AAD アプリケーション ID (手順 1 で取得)

- Azure App Service URL (手順 1 で取得したもの、たとえば、 https://fbconnector.azurewebsites.net)

- APISecretKey (手順 2 で作成した)
