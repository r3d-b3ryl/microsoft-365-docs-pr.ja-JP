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
ms.openlocfilehash: 6544aed693d9f2e7249ce44ed3ef6185ab32af9b
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035524"
---
# <a name="overview"></a>概要

Microsoft Managed Desktop は、従業員の Windows デバイスの展開と更新を維持するように設計されたエンタープライズ クラウドのお客様向け IT-as-a-Service (ITaaS) サービスです。 IT サービスの管理と運用、セキュリティとインシデント対応の監視、ユーザー サポートの提供も行います。 このドキュメントでは、Microsoft Managed Desktop のデータ プラットフォームとプライバシーコンプライアンスの詳細について説明します。

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Managed Desktop データ ソースと目的

Microsoft Managed Desktop は、企業のお客様にサービスを提供し、さまざまなソースからのデータを使用して、お客様の登録済みデバイスを適切に管理します。 Azure Active Directory、Microsoft Intune、Microsoft Windows 10、Microsoft Defender for Endpoint などのこれらのソースは、Microsoft Managed Desktop が管理するデバイスの包括的なビューを提供します。 このサービスでは、次のMicrosoft サービスを使用して、Microsoft Managed Desktop が ITaaS 機能を提供できます。

- [Microsoft Windows 10 Enterprise](/windows/windows-10/) - デバイスのセットアップ エクスペリエンスの管理、他のサービスへの接続の管理、IT プロの運用サポートを行います。
- [Windowsビジネス向け更新](/windows/deployment/update/waas-manage-updates-wufb)プログラム - Windows 10 Enterprise診断データを使用して、更新プログラムに関する追加情報Windows 10します。 
- [Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview) – デバイスの管理とデータのセキュリティ保護を行います。
  - [Microsoft Azure Active Directory](/azure/active-directory/) - すべてのユーザー アカウントの認証と識別を行います。 
  - [Microsoft Intune](/mem/intune/) – デバイス構成、デバイス管理、アプリケーション管理を配布します。
  - [Endpoint Analytics](/mem/analytics/overview) – デバイスとアプリの使用状況に関する分析的な分析情報を提供します。
  - [Windows自動パイロット –](/microsoft-365/windows/windows-autopilot)デバイスのプロビジョニングと展開に使用します。
  - [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/) – デバイス のセキュリティ監視やセキュリティ インテリジェンス データなどのセキュリティ サービスを提供します。
- [Microsoft Managed Desktop](https://endpoint.microsoft.com/#home)  – サービスの実行中に、お客様が提供するか、サービスによって生成されたデータ。
- [Microsoft 365 Apps for enterprise](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) – Microsoft 365 Apps の管理のため。

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop のデータ プロセスとストレージ

Microsoft Managed Desktop は、企業のお客様にサービスを提供するために、複数の Microsoft 製品およびサービスのデータに依存しています。 登録済みデバイスの保護と維持の目標を達成するために、これらのサービスから Microsoft Managed Desktop にデータを処理してコピーします。  データを処理する場合、オンライン サービス条項および Microsoft プライバシーに関する声明[](https://www.microsoft.com/licensing/product-licensing/products)で参照されている、お客様が提供する文書化された指示[に従います](https://privacy.microsoft.com/privacystatement)。 Microsoft Managed Desktop のプロセッサ業務には、適切な機密性、セキュリティ、回復性の確保が含まれます。 Microsoft Managed Desktop では、個人を特定できるデータを適切に処理するために、追加のプライバシーとセキュリティ対策を採用しています。 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktop データ ストレージとスタッフの場所

Microsoft Managed Desktop は、そのデータを米国の Azure データ センターに格納します。 Microsoft Managed Desktop および他のサービスによって取得された個人データは、サービスの運用を維持するために必要です。 Microsoft Managed Desktop からデバイスが削除された場合、Microsoft Defender for Endpoint によって収集されたアラート データを除き、最大 30 日間個人データを保持します。これはセキュリティ上の目的で 180 日間保存されます。 データ保持の詳細については、「[Microsoft 365 のデータの保持、削除、および破棄](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)」を参照してください。

Microsoft Managed Desktop Engineering Operations および Security Operations チームは、米国とインドに位置しています。 

### <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10診断データ

Microsoft Managed Desktop[では、Windows 10](/windows/privacy/windows-diagnostic-data)拡張診断データを使用して、セキュリティWindows最新の状態に保ち、問題のトラブルシューティングを行い、製品の改善を行います。 拡張診断データ設定には、Microsoft Managed Desktop に登録されているデバイスとその設定、機能、デバイスの正常性に関する詳細情報が含まれています。 拡張診断データを選択すると、必要な診断データを含むデータが収集されます。 診断[データの設定とWindowsの](/windows/privacy/changes-to-windows-diagnostic-data-collection)詳細については、「診断データコレクションの変更Windows 10変更」を参照してください。

診断データの用語は、将来のバージョンのバージョンで変更Windows。 Microsoft Managed Desktop は、サービスに必要なデータのみを処理します。 これは、診断レベルがオプションに変わることを意味しますが、Microsoft Managed Desktop は、サービスに必要な診断データ収集を微調整するための限られた診断ポリシーを実装します。 詳細については、「診断データ収集[の変更点Windows」を参照してください](/windows/privacy/changes-to-windows-diagnostic-data-collection)。

Microsoft Managed Desktop は、アプリケーションやデバイスの信頼性、パフォーマンス情報など、登録済みデバイスから発生する Windows 10 オプションの診断データからシステム レベルのデータのみを処理して保存します。 Microsoft Managed Desktop は、チャットやブラウザーの履歴、音声、テキスト、音声データなどのお客様の個人データを処理および保存します。 

Microsoft Windows 10 の診断データコレクションの詳細については、「Microsoft Privacy Statement」の「個人データの保存と処理」セクションを参照してください。 [](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)

### <a name="microsoft-windows-update-for-business"></a>Microsoft Windowsビジネス向け更新プログラム
Microsoft Windows Update for Business は、更新プログラムのWindowsの状態とエラーを分析するために、ユーザー診断からのデータを使用します。 Microsoft Managed Desktop は、このデータを活用し、このデータを使用して問題の軽減と解決を行い、登録済みのすべてのデバイスが定義済みの更新プログラムのケイデンスに基づいて最新の情報を提供します。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Microsoft Managed Desktop で使用されるデータの識別は、Azure Active Directory (Azure AD) によって、企業向け Microsoft Apps や Azure などの Microsoft オンライン サービスを購読する際に組織が提供する場所に基づいて地理的な場所に格納されます。 Microsoft Managed Desktop で使用されるデータの識別は、Microsoft Apps for enterprise や Azure などの Microsoft オンライン サービスを購読する際に、組織が提供する場所に基づいて、Azure AD によって地理的な場所に格納されます。 データの場所のAzure AD詳細については、「Azure Active Directory [- データの場所」を参照してください。](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intuneおよびサービスをサポートするために、Microsoft Managed Desktop にデータを収集、処理、および共有します。 Intune [で収集されるデータの詳細については、「Intune](/mem/intune/protect/privacy-data-collect) でのデータ収集」を参照してください。 

データの場所の詳細Microsoft Intune、顧客データの保存場所[Microsoft 365を参照してください](/microsoft-365/enterprise/o365-data-locations)。 Intune は、管理者が顧客データに対して行った保存場所の選択を尊重します。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint
Microsoft Defender for Endpoint は、管理、追跡、およびレポートの目的で Microsoft Managed Desktop に登録されているデバイスの情報を収集および保存します。 収集される情報には、ファイル データ (ファイル名、サイズ、ハッシュなど)、プロセス データ (実行中のプロセス、ハッシュ)、レジストリ データ、ネットワーク接続データ、デバイスの詳細 (デバイス識別子、デバイス名、オペレーティング システムのバージョンなど) が含まれます。 [Microsoft Defender for Endpoint のデータ](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)収集とストレージの場所の詳細については、「Microsoft Defender for Endpoint data storage and privacy」を参照してください。 

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise 
Microsoft 365 Apps for enterpriseデータを収集し、Microsoft Managed Desktop と共有することで、Microsoft Managed Desktop によって管理される定義済みの更新チャネルに基づいて、これらのアプリが最新バージョンで最新のバージョンに更新されます。 Microsoft [Defender for Endpoint のデータストレージとプライバシーを参照](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)して、Microsoft 365 Appsのデータ収集と保存場所の詳細について説明します。

## <a name="major-data-change-notification"></a>メジャー データ変更通知
Microsoft Managed Desktop は、サービス通信フレームワークで説明されている変更管理プロセスに従います。 Microsoft は、セキュリティ インシデントとサービスMicrosoft 365変更の両方について、Microsoft メッセージ センターと Microsoft Managed Desktop Admin ポータルを通じてお客様に通知します。 収集されたデータの種類と格納場所に対する変更は、重要な変更と見なされます。 この変更に関する詳細な通知は、製品およびサービスの標準的な方法と同様に、少なくとも 30 日間Microsoft 365提供します。 詳細については、「サービスの変更 [と通信」を参照してください](/microsoft-365/managed-desktop/service-description/servicechanges)。

## <a name="compliance"></a>コンプライアンス
Microsoft Managed Desktop は外部監査を受け、包括的なコンプライアンス提供のセットを取得しました。 詳細については、「Microsoft Managed Desktop [Compliance」を参照してください](/microsoft-365/managed-desktop/intro/compliance)。 監査レポートは、Microsoft サービスセキュリティポータルでダウンロードできます。これは、Microsoft[サービス](https://aka.ms/stp)オンライン サービスのEnterprise機能します。 (Microsoft Managed Desktop は、これらのドキュメント内のカテゴリ "監視と管理"の下に表示されます。

### <a name="data-subject-requests"></a>データ主体要求
Microsoft Managed Desktop は GDPR および CCPA のプライバシー規制に従い、データ主体に個人データに対する特定の権利を与えます。 これらの権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、または別のコントローラーに移動するための電子形式での受信が含まれます。 データ主体要求 (DSR) の一般的な詳細については、「データ主体要求」および [「GDPR および CCPA」を参照してください](/compliance/regulatory/gdpr-data-subject-requests)。

Microsoft Managed Desktop ケース管理システムによって収集されたデータに関するデータ主体要求を実行するには、以下を参照してください。

- Microsoft Defender for Endpoint アラートのデータ: セキュリティ管理者は、管理ポータルでレポート要求を送信することで、Microsoft Defender for Endpoint アラートに関連する個人データの削除または抽出を [要求できます](https://aka.ms/memadmin)。 要求で、[要求の変更] 、 **カテゴリ [** セキュリティ]、および **[その** 他] のサブカテゴリを選択 **します**。 要求の説明に関連するデバイス名を指定します。
- Microsoft Managed Desktop サポート要求からのデータ: IT 管理者は、管理者ポータルでレポート要求を提出することにより、個人データ関連のサポート要求の削除または抽出を [要求できます](https://aka.ms/memadmin)。 要求で、[要求の変更] 、 **カテゴリ [** セキュリティ]、および **[その** 他] のサブカテゴリを選択 **します**。 要求の説明に関連するデバイス名またはユーザー名を指定します。

サービスに関連する他の製品の DSRs については、次の記事を参照してください。

- Windows[診断データ](/compliance/regulatory/gdpr-dsr-windows)
- Microsoft [Intune データ](/compliance/regulatory/gdpr-dsr-intune)
- Azure Active [Directory データ](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>法務
**組織のお客様が提供する製品のエンド ユーザーへの Microsoft のプライバシーに関する通知** - [Microsoft プライバシー ステートメント](https://privacy.microsoft.com/privacystatement)は、エンド ユーザーが職場アカウントを使用して Microsoft 製品にサインインすると、組織が (プライバシー関連の設定の制御を含めて) ユーザーのアカウントを制御および管理し、データにアクセスして処理することができ、b) Microsoft が組織およびエンド ユーザーにサービスを提供するためにデータを収集および処理する場合があることを通知します。
