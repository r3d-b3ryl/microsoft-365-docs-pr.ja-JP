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
description: Microsoft 365 コンプライアンス センター&を使用して、Facebook Business ページから Microsoft 365 に & アーカイブ データをインポートする方法について説明します。
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921737"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Facebook データをアーカイブするコネクタをセットアップする (プレビュー)

Microsoft 365 コンプライアンス センターのコネクタを使用して、Facebook Business ページから Microsoft 365 にデータをインポートおよびアーカイブします。 コネクタをセットアップして構成した後、(スケジュールに基づいて) Facebook Business ページに接続し、Facebook アイテムのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

Facebook データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Facebook データに適用できます。 たとえば、メールボックスが訴訟ホールドに置かれたり、アイテム保持ポリシーに割り当てられたりすると、Facebook データは保持されます。 コンテンツ検索を使用してサード パーティのデータを検索するか、Facebook データが保存されているメールボックスを高度な電子情報開示ケースの保管担当者に関連付けできます。 コネクタを使用して Microsoft 365 で Facebook データをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Facebook Business ページのコネクタを設定するための前提条件

Microsoft 365 コンプライアンス センターでコネクタをセットアップして構成し、組織の Facebook Business ページからデータをインポートおよびアーカイブするには、以下の前提条件を満たしてください。 

- 組織のビジネス ページ用の Facebook アカウントが必要です (コネクタをセットアップする場合は、このアカウントにサインインする必要があります)。 現時点では、Facebook Business ページからのみデータをアーカイブできます。個々の Facebook プロファイルからデータをアーカイブできない。

- 組織に有効な Azure サブスクリプションが必要です。 既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。

    - [無料の 1 年間 Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free)

    - [Pay-As-Go Azure サブスクリプションにサインアップする](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 サブスクリプションに含まれる無料の Azure [Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) サブスクリプションは、セキュリティ コンプライアンス センター&サポートしていません。

- Facebook Business ページのコネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 件を超える Facebook Business アイテムがある場合、それらのアイテムはいずれも Microsoft 365 にインポートされません。

- Microsoft 365 コンプライアンス センター (手順 5) でカスタム コネクタを設定するユーザーには、Exchange Online のメールボックスインポートエクスポートの役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順は、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、Facebook コネクタの手順 4 と手順 5 で実装する Web アプリ リソースに対応します。 

手順については、「Azure Active Directory で [アプリを作成する」を参照してください](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)。

この手順が完了すると (前の手順を使用して)、次の情報をテキスト ファイルに保存します。 これらの値は、展開プロセスの後の手順で使用されます。

- AAD アプリケーション ID

- AAD アプリケーション シークレット

- テナント ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: GitHub から Azure アカウントにコネクタ Web サービスを展開する

次の手順では、Facebook API を使用して Facebook アカウントに接続し、データを抽出して Microsoft 365 にインポートできる Facebook Business ページ コネクタ アプリのソース コードを展開します。 組織に展開する Facebook コネクタは、この手順で作成した Azure Storage の場所に、Facebook Business ページからアイテムをアップロードします。 Microsoft 365 コンプライアンス センター (手順 5) で Facebook ビジネス ページ コネクタを作成すると、インポート サービスは、Azure Storage の場所から Microsoft 365 組織のメールボックスに Facebook ビジネス ページ データをコピーします。 「前提条件」セクションで [説明したように](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) 、Azure ストレージ アカウントを作成するには、有効な Azure サブスクリプションが必要です。

詳細な手順については、「コネクタ Web サービスを GitHub から Azure アカウントに展開 [する」を参照してください](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

この手順を完了する手順では、次の情報を提供します。

- APISecretKey: この手順の完了時に、このシークレットを作成します。 手順 5 で使用します。

- TenantId: 手順 1 の Azure Active Directory で Facebook コネクタ アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。

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

- Azure Active Directory アプリケーション ID (手順 1 で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Microsoft 365 コンプライアンス センターで Facebook Business ページ コネクタをセットアップする

最後の手順は、Microsoft 365 コンプライアンス センターでコネクタをセットアップし、Facebook Business ページから Microsoft 365 の指定されたメールボックスにデータをインポートすることです。 この手順を完了すると、Microsoft 365 インポート サービスは、Facebook Business ページから Microsoft 365 へのデータのインポートを開始します。

手順については、「 [手順 5: Microsoft 365](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)コンプライアンス センターで Facebook コネクタをセットアップする」を参照してください。 

この手順の完了時 (手順の手順に従って) は、次の情報 (手順の完了後にテキスト ファイルにコピーした情報) を提供します。

- AAD アプリケーション ID (手順 1 で取得)

- Azure アプリ サービスの URL (手順 1 で取得されます。たとえば、 https://fbconnector.azurewebsites.net)

- APISecretKey (手順 2 で作成した)