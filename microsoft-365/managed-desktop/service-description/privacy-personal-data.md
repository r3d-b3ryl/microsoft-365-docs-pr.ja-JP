---
title: プライバシーおよび個人データ
description: サービスによって収集、保存、および使用されるデータの詳細
keywords: GDPR、保有期間、削除、ストレージ、保有期間、処理、セキュリティ、監査
ms.service: m365-md
ms.sitesec: library
author: tiaraquan
manager: dougeby
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: medium
ms.openlocfilehash: e7c9912e3890d9b13003c7f3264490f67c4fc305
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128348"
---
# <a name="privacy"></a>プライバシー

Microsoft Managed Desktopは、従業員のWindows デバイスのデプロイと更新を維持するように設計されたエンタープライズ クラウドのお客様向けのサービスとしての IT (ITaaS) サービスです。

また、IT サービスの管理と運用、セキュリティとインシデント対応の監視、ユーザー サポートも提供されます。 この記事では、Microsoft Managed Desktopのデータ プラットフォームとプライバシーコンプライアンスの詳細について説明します。

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>データ ソースと目的をMicrosoft Managed Desktopする

Microsoft Managed Desktopは、企業のお客様にサービスを提供し、さまざまなソースからのデータを使用して、顧客の登録済みデバイスを適切に管理します。

これらのソースには、Azure Active Directory、Microsoft Intune、Microsoft Windows 10、Microsoft Defender for Endpointが含まれます。 Microsoft Managed Desktopが管理するデバイスの包括的なビューを提供します。 また、このサービスでは、次のMicrosoft サービスを使用して、Microsoft Managed Desktopが ITaaS 機能を提供できるようにします。

| データ ソース | 用途 |
| ------ | ------ |
| [Microsoft Windows 10 Enterprise](/windows/windows-10/) | デバイスのセットアップ エクスペリエンスの管理、他のサービスへの接続の管理、IT 担当者の運用サポート。 |
| [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) | Windows 10 Enterprise診断データを使用して、Windows 10更新に関する追加情報を提供します。 |
| [Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview) | デバイス管理とデータのセキュリティ保護。 次のデータ ソースは、Microsoft エンドポイント マネージャーに該当します。<br><ul><li>[Microsoft Azure Active Directory](/azure/active-directory/): すべてのユーザー アカウントの認証と識別。</li><li>[Microsoft Intune](/mem/intune/): デバイス構成の配布、デバイス管理、アプリケーション管理。</li><li>[Endpoint Analytics](/mem/analytics/overview): デバイスとアプリの使用状況に関する分析分析情報。</li><li>[Windows Autopilot](/microsoft-365/windows/windows-autopilot): デバイスのプロビジョニングと展開。</li><li>[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/): デバイスのセキュリティ監視やセキュリティ インテリジェンス データなどのセキュリティ サービスを提供します。</li></ul>
| [Microsoft マネージド デスクトップ](https://endpoint.microsoft.com/#home) | サービスの実行中に顧客が提供したデータ、またはサービスによって生成されたデータ。 |
| [エンタープライズ向けのアプリをMicrosoft 365する](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1)| Microsoft 365 Appsの管理。

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop データ プロセスとストレージ

Microsoft Managed Desktopは、企業のお客様にサービスを提供するために、複数の Microsoft 製品とサービスのデータに依存しています。

登録されたデバイスを保護および維持するために、これらのサービスからMicrosoft Managed Desktopにデータを処理してコピーします。 データを処理する場合、 [オンライン サービスの使用条件](https://www.microsoft.com/licensing/product-licensing/products) と [Microsoft プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)に記載されているように、お客様が指定した文書化された指示に従います。

Microsoft Managed Desktopのプロセッサの職務には、適切な機密性、セキュリティ、回復性の確保が含まれます。 Microsoft Managed Desktopは、個人を特定できるデータの適切な処理を確保するために、追加のプライバシーとセキュリティ対策を採用しています。

## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktopデータストレージとスタッフの場所

Microsoft Managed Desktopは、そのデータを米国の Azure データ センターに格納します。

サービスの運用を維持するには、Microsoft Managed Desktopおよびその他のサービスによって取得された個人データが必要です。 デバイスがMicrosoft Managed Desktopから削除された場合、個人データは最大 30 日間保持されます。 ただし、Microsoft Defender for Endpointによって収集されたアラート データは、セキュリティ上の目的で 180 日間保存されます。 データ保持の詳細については、「[Microsoft 365 のデータの保持、削除、および破棄](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)」を参照してください。

Microsoft Managed Desktopエンジニアリング運用チームとセキュリティ運用チームは、米国、インド、ルーマニアにあります。

### <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10診断データ

Microsoft Managed Desktopでは[、Windows 10強化された診断データ](/windows/privacy/windows-diagnostic-data)を使用して、セキュリティWindows最新の状態に保ち、問題のトラブルシューティングを行い、製品の改善を行います。

強化された診断データ設定には、Microsoft Managed Desktopに登録されているデバイスとその設定、機能、およびデバイスの正常性に関する詳細情報が含まれています。 強化された診断データが選択されると、必要な診断データを含むデータが収集されます。 詳細については、「[Windows 10診断データ設定とデータ収集に](/windows/privacy/changes-to-windows-diagnostic-data-collection)関するWindows診断データ収集の変更」を参照してください。

診断データの用語は、今後のバージョンのWindowsで変更される予定です。 Microsoft Managed Desktopは、サービスに必要なデータのみを処理することにコミットされます。 これは、診断レベルが **省略可能** に変更されることを意味しますが、Microsoft Managed Desktopは、サービスに必要な診断データ収集を微調整するために限られた診断ポリシーを実装します。 詳細については、「[Windows診断データ収集の変更](/windows/privacy/changes-to-windows-diagnostic-data-collection)」を参照してください。

Microsoft Managed Desktopは、アプリケーションやデバイスの信頼性、パフォーマンス情報など、登録済みのデバイスから生成されたオプションの診断データWindows 10システム レベルのデータのみを処理して格納します。 Microsoft Managed Desktopは、チャットやブラウザーの履歴、音声、テキスト、音声データなどの顧客の個人データを処理して保存しません。

Microsoft Windows 10の診断データ収集の詳細については、Microsoft プライバシーに関する声明の「[個人データの保存場所と処理場所](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)」セクションを参照してください。

### <a name="microsoft-windows-update-for-business"></a>Microsoft Windows Update for Business

Microsoft Windows Update for Business では、Windows診断のデータを使用して、更新の状態とエラーを分析します。 Microsoft Managed Desktopでは、このデータを使用して、定義済みの更新プログラムの周期に基づいて、登録されているすべてのデバイスが最新の状態になるように問題を軽減し、解決します。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft Managed Desktopによって使用されるデータの識別は、地理的な場所にAzure Active Directory (Azure AD) によって格納されます。 地理的な場所は、Enterpriseや Azure のMicrosoft Appsなど、Microsoft オンライン サービスのサブスクライブ時に組織によって提供される場所に基づいています。 Azure AD データの場所の詳細については、「[Azure Active Directory - データの場所」を参照してください。](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intuneは、ビジネス運用とサービスをサポートするために、データを収集、処理、およびMicrosoft Managed Desktopに共有します。 Intuneで収集されるデータの詳細については、「Intune [のデータ収集](/mem/intune/protect/privacy-data-collect)」を参照してください。

Microsoft Intuneデータの場所の詳細については、「[Microsoft 365顧客データの保存場所](/microsoft-365/enterprise/o365-data-locations)」を参照してください。 Intuneは、顧客データに対して管理者が行った保存場所の選択を尊重します。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

Microsoft Defender for Endpointは、管理、追跡、レポートの目的でMicrosoft Managed Desktopに登録されているデバイスの情報を収集して格納します。 収集される情報には、次のものが含まれます。

- ファイル データ (ファイル名、サイズ、ハッシュなど)
- プロセス データ (実行中のプロセス、ハッシュ)
- レジストリ データ
- ネットワーク接続データ
- デバイスの詳細 (デバイス識別子、デバイス名、オペレーティング システムのバージョンなど)

Microsoft Defender for Endpointのデータ収集場所とストレージの場所の詳細については、「[Microsoft Defender for Endpointデータストレージとプライバシー](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)」を参照してください。

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

EnterpriseのMicrosoft 365 Appsは、Microsoft Managed Desktopとデータを収集して共有し、それらのアプリが最新バージョンで最新であることを確認します。 これらの更新プログラムは、Microsoft Managed Desktopによって管理される定義済みの更新チャネルに基づいています。 Microsoft 365 Appsのデータ収集場所とストレージの場所の詳細については、「[Microsoft Defender for Endpointデータストレージとプライバシー](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)」を参照してください。

## <a name="major-data-change-notification"></a>メジャー データ変更通知

Microsoft Managed Desktopは、サービス通信フレームワークで説明されているように、変更制御プロセスに従います。

セキュリティ インシデントとサービスの大きな変更の両方について、Microsoft 365 メッセージ センターとMicrosoft Managed Desktop管理ポータルを通じてお客様に通知します。

収集されたデータの種類と格納場所に対する変更は、重大な変更と見なされます。 Microsoft 365製品とサービスの標準的なプラクティスと同様に、この変更に関する少なくとも 30 日間の高度な通知を提供します。 詳細については、「サービスの [変更と通信](/microsoft-365/managed-desktop/service-description/servicechanges)」を参照してください。

## <a name="compliance"></a>コンプライアンス

Microsoft Managed Desktopは外部監査を受け、包括的な一連のコンプライアンス オファリングを取得しました。 詳細については、「コンプライアンス」を [参照](/microsoft-365/managed-desktop/intro/compliance)してください。 監査レポートは、Microsoft Enterprise Online Services の中央リポジトリとして機能する Microsoft [Service Trust Portal](https://aka.ms/stp) でダウンロードできます。 Microsoft Managed Desktopは、これらのドキュメントの [監視と管理] カテゴリに一覧表示されます。

### <a name="data-subject-requests"></a>データ主体要求

Microsoft Managed Desktop GDPR および CCPA のプライバシー規制に従います。これにより、データ主体は個人データに対する特定の権利を付与されます。

これらの権限には、次のものが含まれます。

- 個人データのコピーを取得する
- 修正を要求する
- 処理の制限
- 削除する
- 別のコントローラーに移動できるように電子形式で受け取ります。

データ 主体要求 (DSR) の詳細については、「 [データ主体要求と GDPR と CCPA](/compliance/regulatory/gdpr-data-subject-requests)」を参照してください。

Microsoft Managed Desktop ケース管理システムによって収集されたデータに対するデータ主体要求を実行するには、次のデータ主体の要求を参照してください。

| データ主体要求 | 説明 |
| ------ | ------ |
| Microsoft Defender for Endpointアラートからのデータ | セキュリティ管理者は、[管理者ポータル](https://aka.ms/memadmin)でレポート要求を送信することで、Microsoft Defender for Endpointアラートに関連する個人データの削除または抽出を要求できます。 <br><br> 以下の情報を指定します。 <br><ul><li>要求の種類: 要求を変更する</li><li>カテゴリ: セキュリティ</li><li>サブカテゴリ: その他</li><li>説明: 関連するデバイス名を指定します。</li></ul> |
| Microsoft Managed Desktopサポート要求からのデータ | IT 管理者は、 [管理者ポータル](https://aka.ms/memadmin)でレポート要求を送信することで、個人データ関連のサポート要求の削除または抽出を要求できます。 <br><br> 以下の情報を指定します。 <ul><li>要求の種類: 要求を変更する</li><li>カテゴリ: セキュリティ</li><li>サブカテゴリ: その他</li><li>説明: 関連するデバイス名またはユーザー名を指定します。</li></ul>

サービスに関連する他の製品の DSR については、次の記事を参照してください。

- [診断データ](/compliance/regulatory/gdpr-dsr-windows)をWindowsする
- Microsoft [Intune データ](/compliance/regulatory/gdpr-dsr-intune)
- Azure Active [Directory データ](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>法務

**組織のお客様が提供する製品のエンド ユーザーに対する Microsoft のプライバシーに関する通知**:

[Microsoft プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)は、職場アカウントを使用して Microsoft 製品にサインインすると、エンド ユーザーに通知します。

1. 組織は、(プライバシー関連の設定の制御を含む) アカウントを制御および管理し、データにアクセスして処理できます。
1. Microsoft は、組織およびエンド ユーザーにサービスを提供するために、データを収集して処理する場合があります。
