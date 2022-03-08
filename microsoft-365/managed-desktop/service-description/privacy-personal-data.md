---
title: プライバシーおよび個人データ
description: サービスによって収集、保存、および使用されるデータの詳細
keywords: GDPR、保持、削除、ストレージ、保持、処理、セキュリティ、監査
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
ms.openlocfilehash: c70b15a3d35dc4b19c5961e9fbe0404780c12309
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330259"
---
# <a name="privacy"></a>プライバシー

Microsoft Managed Desktop は、従業員の Windows デバイスの展開と更新を維持するように設計されたエンタープライズ クラウド顧客向け IT-as-a-Service (ITaaS) サービスです。

IT サービスの管理と運用、セキュリティとインシデント対応の監視、ユーザー サポートも提供します。 この記事では、Microsoft Managed Desktop のデータ プラットフォームとプライバシーコンプライアンスの詳細について説明します。

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Managed Desktop データ ソースと目的

Microsoft Managed Desktop は、企業のお客様にサービスを提供し、さまざまなソースのデータを使用して、お客様の登録済みデバイスを適切に管理します。

これらのソースには、Azure Active Directory、Microsoft Intune、Microsoft Windows 10、Microsoft Defender for Endpoint が含まれます。 Microsoft Managed Desktop が管理するデバイスの包括的なビューを提供します。 このサービスでは、次のMicrosoft サービスを使用して、Microsoft Managed Desktop が ITaaS 機能を提供できます。

| データ ソース | 用途 |
| ------ | ------ |
| [Microsoft Windows 10 Enterprise](/windows/windows-10/) | デバイスセットアップエクスペリエンスの管理、他のサービスへの接続の管理、IT プロの運用サポート。 |
| [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) | 診断Windows 10 Enterpriseを使用して、更新プログラムに関する追加情報Windows 10します。 |
| [Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview) | デバイスの管理とデータのセキュリティ保護。 次のデータ ソースは、次のMicrosoft エンドポイント マネージャー。<br><ul><li>[Microsoft Azure Active Directory](/azure/active-directory/): すべてのユーザー アカウントの認証と ID。</li><li>[Microsoft Intune](/mem/intune/): デバイス構成の配布、デバイス管理、およびアプリケーション管理。</li><li>[Endpoint Analytics](/mem/analytics/overview): デバイスとアプリの使用状況に関する分析分析情報。</li><li>[Windows自動操縦](/microsoft-365/windows/windows-autopilot): デバイスのプロビジョニングと展開。</li><li>[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/): デバイス セキュリティ監視やセキュリティ インテリジェンス データなどのセキュリティ サービスを提供します。</li></ul>
| [Microsoft マネージド デスクトップ](https://endpoint.microsoft.com/#home) | お客様から提供されたデータ、またはサービスの実行中にサービスによって生成されたデータ。 |
| [Microsoft 365向けアプリ](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1)| 管理Microsoft 365 Apps。

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop のデータ プロセスとストレージ

Microsoft Managed Desktop は、企業のお客様にサービスを提供するために、複数の Microsoft 製品およびサービスのデータに依存しています。

登録済みデバイスを保護および維持するために、これらのサービスから Microsoft Managed Desktop にデータを処理およびコピーします。 データを処理する際には、オンライン サービス条項および Microsoft プライバシーに関する声明で参照[](https://www.microsoft.com/licensing/product-licensing/products)されている、お客様が提供する文書化された指示[に従います](https://privacy.microsoft.com/privacystatement)。

Microsoft Managed Desktop のプロセッサ業務には、適切な機密性、セキュリティ、回復性の確保が含まれます。 Microsoft Managed Desktop では、個人を特定できるデータを適切に処理するために、追加のプライバシーとセキュリティ対策を採用しています。

## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktop データ ストレージとスタッフの場所

Microsoft Managed Desktop は、そのデータを米国の Azure データ センターに格納します。

Microsoft Managed Desktop および他のサービスによって取得された個人データは、サービスの運用を維持するために必要です。 デバイスが Microsoft Managed Desktop から削除された場合、個人データは最大 30 日間保持されます。 ただし、Microsoft Defender for Endpoint によって収集されたアラート データは、セキュリティ上の目的で 180 日間保存されます。 データ保持の詳細については、「[Microsoft 365 のデータの保持、削除、および破棄](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)」を参照してください。

Microsoft Managed Desktop Engineering Operations および Security Operations チームは、米国とインドに位置しています。

### <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10診断データ

Microsoft Managed Desktop では、Windows 10[拡張](/windows/privacy/windows-diagnostic-data)診断データを使用して、セキュリティWindows最新の状態に保ち、問題のトラブルシューティングを行い、製品の改善を行います。

拡張診断データ設定には、Microsoft Managed Desktop に登録されているデバイスとその設定、機能、デバイスの正常性に関する詳細情報が含まれています。 拡張診断データを選択すると、必要な診断データを含むデータが収集されます。 詳細については、「診断データの[設定とデータWindowsに](/windows/privacy/changes-to-windows-diagnostic-data-collection)関する診断データコレクションWindows 10変更」を参照してください。

診断データの用語は、将来のバージョンのバージョンで変更Windows。 Microsoft Managed Desktop は、サービスに必要なデータのみを処理します。 これは、診断レベルがオプションに変わることを意味しますが、Microsoft Managed Desktop は、サービスに必要な診断データ収集を微調整するための限られた診断ポリシーを実装します。 詳細については、「診断データ収集[に対する変更Windows参照してください](/windows/privacy/changes-to-windows-diagnostic-data-collection)。

Microsoft Managed Desktop は、アプリケーションやデバイスの信頼性、パフォーマンス情報など、登録済みデバイスから発生する Windows 10 オプションの診断データからシステム レベルのデータを処理して保存します。 Microsoft Managed Desktop は、チャットやブラウザーの履歴、音声、テキスト、音声データなどの顧客の個人データを処理および保存します。

Microsoft Windows 10 の診断データコレクションの詳細については、「Microsoft Privacy Statement」の「個人[](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)データの保存と処理」セクションを参照してください。

### <a name="microsoft-windows-update-for-business"></a>Microsoft Windowsビジネス向け更新プログラム

Microsoft Windows Update for Business では、更新プログラムのWindowsのデータを使用して、更新の状態とエラーを分析します。 Microsoft Managed Desktop では、このデータを使用して問題を軽減および解決し、すべての登録済みデバイスが定義済みの更新プログラムのケイデンスに基づいて最新の情報に更新されます。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft Managed Desktop で使用されるデータの識別は、Azure Active Directory (Azure AD) によって地理的な場所に保存されます。 地理的な場所は、Microsoft オンライン サービスを購読する際に組織が提供する場所に基づいており、Microsoft Appsおよび Azure Enterpriseなどです。 データの場所のAzure AD詳細については、「Azure Active Directory [- データの場所」を参照してください。](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intuneおよびサービスをサポートするために、Microsoft Managed Desktop にデータを収集、処理、および共有します。 Intune で収集されるデータの詳細については、「Intune での [データ収集」を参照してください。](/mem/intune/protect/privacy-data-collect)

データの場所のMicrosoft Intune詳細については、「顧客データMicrosoft 365保存場所[」を参照してください](/microsoft-365/enterprise/o365-data-locations)。 Intune は、管理者が顧客データに対して行った保存場所の選択を尊重します。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

Microsoft Defender for Endpoint は、管理、追跡、およびレポートの目的で Microsoft Managed Desktop に登録されているデバイスの情報を収集および保存します。 収集される情報には、次の情報が含まれます。

- ファイル データ (ファイル名、サイズ、ハッシュなど)
- プロセス データ (実行中のプロセス、ハッシュ)
- レジストリ データ
- ネットワーク接続データ
- デバイスの詳細 (デバイス識別子、デバイス名、オペレーティング システムのバージョンなど)

Microsoft Defender for Endpoint のデータ収集とストレージの場所の詳細については、「 [Microsoft Defender for Endpoint data storage and privacy」を参照してください](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)。

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

Microsoft 365 AppsのEnterpriseを収集し、Microsoft Managed Desktop と共有して、これらのアプリが最新バージョンで最新のバージョンに更新されるのを確認します。 これらの更新プログラムは、Microsoft Managed Desktop によって管理される定義済みの更新チャネルに基づいて行います。 データ収集とストレージMicrosoft 365 Apps詳細については、「[Microsoft Defender for Endpoint data storage and privacy」を参照してください](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)。

## <a name="major-data-change-notification"></a>メジャー データ変更通知

Microsoft Managed Desktop は、サービス通信フレームワークで説明されている変更管理プロセスに従います。

Microsoft は、Microsoft 365 メッセージ センターと Microsoft Managed Desktop Admin ポータルを通じて、セキュリティ インシデントとサービスの大きな変更の両方についてお客様に通知します。

収集されたデータの種類と保存場所に対する変更は、重要な変更と見なされます。 この変更に関する詳細な通知は、製品とサービスの標準的なMicrosoft 365 30 日以上提供します。 詳細については、「サービスの変更 [と通信」を参照してください](/microsoft-365/managed-desktop/service-description/servicechanges)。

## <a name="compliance"></a>コンプライアンス

Microsoft Managed Desktop は外部監査を受け、包括的なコンプライアンス提供のセットを取得しました。 詳細については、「コンプライアンス」を [参照してください](/microsoft-365/managed-desktop/intro/compliance)。 監査レポートは、Microsoft サービスセキュリティポータルでダウンロードできます。これは、Microsoft [サービス](https://aka.ms/stp) オンライン サービスの中央リポジトリEnterprise提供されます。 Microsoft Managed Desktop は、これらのドキュメント内の [監視と管理] カテゴリに一覧表示されます。

### <a name="data-subject-requests"></a>データ主体要求

Microsoft Managed Desktop は GDPR および CCPA のプライバシー規制に従い、データ主体に個人データに対する特定の権利を与えます。

これらの権限には、次のものが含まれます。

- 個人データのコピーの取得
- 修正を要求する
- 処理の制限
- 削除する
- 別のコントローラーに移動できるよう、電子形式で受信します。

データ主体要求 (DSR) の詳細については、「データ主体要求」および「 [GDPR および CCPA」を参照してください](/compliance/regulatory/gdpr-data-subject-requests)。

Microsoft Managed Desktop ケース管理システムによって収集されたデータに対するデータ主体要求を実行するには、次のデータ主体要求を参照してください。

| データ主体要求 | 説明 |
| ------ | ------ |
| Microsoft Defender for Endpoint アラートのデータ | セキュリティ管理者は、管理ポータルでレポート要求を送信することで、Microsoft Defender for Endpoint アラートに関連する個人データの削除または抽出を [要求できます](https://aka.ms/memadmin)。 <br><br> 以下の情報を指定します。 <br><ul><li>要求の種類: 変更要求</li><li>カテゴリ: セキュリティ</li><li>サブカテゴリ: その他</li><li>説明: 関連するデバイス名を指定します。</li></ul> |
| Microsoft Managed Desktop サポート要求からのデータ | IT 管理者は、管理ポータルでレポート要求を提出することで、個人データ関連のサポート要求の削除または抽出を [要求できます](https://aka.ms/memadmin)。 <br><br> 以下の情報を指定します。 <ul><li>要求の種類: 変更要求</li><li>カテゴリ: セキュリティ</li><li>サブカテゴリ: その他</li><li>説明: 関連するデバイス名またはユーザー名を指定します。</li></ul>

サービスに関連する他の製品の DSRs については、次の記事を参照してください。

- Windows[診断データ](/compliance/regulatory/gdpr-dsr-windows)
- Microsoft [Intune データ](/compliance/regulatory/gdpr-dsr-intune)
- Azure Active [Directory データ](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>法務

**組織のお客様が提供する製品のエンド ユーザーに対する Microsoft のプライバシーに関する通知**:

[Microsoft Privacy Statement は、](https://privacy.microsoft.com/privacystatement)エンド ユーザーが仕事用アカウントを使用して Microsoft 製品にサインインするときに、次の情報を通知します。

1. 組織は、自分のアカウント (プライバシー関連の設定の制御を含む) を制御および管理し、データにアクセスして処理できます。
1. Microsoft は、組織およびエンド ユーザーにサービスを提供するためにデータを収集および処理する場合があります。
