---
title: プライバシーと個人データ
description: サービスによって収集、保存、および使用されるデータの詳細
keywords: GDPR、保持、削除、ストレージ、保持、処理、セキュリティ、監査
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: f8c27f5776c41376abd6f9c0e412480e02bab217
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215283"
---
# <a name="overview"></a>概要

Microsoft マネージド デスクトップは、従業員の Windows デバイスの展開と更新を維持するように設計されたエンタープライズ クラウドのお客様向け IT-as-a-Service (ITaaS) サービスです。 IT サービスの管理と運用、セキュリティとインシデント対応の監視、ユーザー サポートの提供も行います。 このドキュメントでは、データ プラットフォームに関するその他の詳細と、データ プラットフォームのプライバシー Microsoft マネージド デスクトップ。

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft マネージド デスクトップデータ ソースと目的

Microsoft マネージド デスクトップ顧客にサービスを提供し、さまざまなソースからのデータを使用して、お客様の登録済みデバイスを適切に管理します。 Azure Active Directory、Microsoft Intune、Microsoft Windows 10、Microsoft Defender for Endpoint など、これらのソースは、管理するデバイスの包括的なMicrosoft マネージド デスクトップ提供します。 また、このサービスでは、次のMicrosoft サービスを使用Microsoft マネージド デスクトップ ITaaS 機能を提供できます。

- [Microsoft Windows 10 Enterprise](/windows/windows-10/) - デバイスのセットアップ エクスペリエンスの管理、他のサービスへの接続の管理、IT プロの運用サポートを行います。
- [Windowsビジネス向け更新](/windows/deployment/update/waas-manage-updates-wufb)プログラム - Windows 10 Enterprise診断データを使用して、更新プログラムに関する追加情報Windows 10します。 
- [Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview) – デバイスの管理とデータのセキュリティ保護を行います。
  - [Microsoft Azure Active Directory](/azure/active-directory/) - すべてのユーザー アカウントの認証と識別を行います。 
  - [Microsoft Intune](/mem/intune/) – デバイス構成、デバイス管理、アプリケーション管理を配布します。
  - [Endpoint Analytics](/mem/analytics/overview) – デバイスとアプリの使用状況に関する分析的な分析情報を提供します。
  - [Windows自動パイロット –](/microsoft-365/windows/windows-autopilot)デバイスのプロビジョニングと展開に使用します。
  - [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/) – デバイス のセキュリティ監視やセキュリティ インテリジェンス データなどのセキュリティ サービスを提供します。
- [Microsoft マネージド デスクトップ](https://endpoint.microsoft.com/#home)– サービスの実行中に顧客が提供したデータ、またはサービスによって生成されたデータ。
- [Microsoft 365企業向けアプリの管理](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1)を行Microsoft 365 Apps。

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft マネージド デスクトップのプロセスとストレージ

Microsoft マネージド デスクトップは、複数の Microsoft 製品およびサービスのデータに依存して、エンタープライズのお客様にサービスを提供します。 登録済みデバイスの保護と維持の目標を達成するために、これらのサービスからデータを処理し、Microsoft マネージド デスクトップ。 データを処理する際には、オンライン サービス条項および Microsoft プライバシーに関する声明で参照されている、お客様が提供する文書化された指示に従います。 データを処理する場合、オンライン サービス条項および Microsoft プライバシーに関する声明[](https://www.microsoft.com/licensing/product-licensing/products)で参照されている、お客様が提供する文書化された指示[に従います](https://privacy.microsoft.com/privacystatement)。 Microsoft マネージド デスクトップには、適切な機密性、セキュリティ、回復性の確保が含まれます。 Microsoft マネージド デスクトップ、個人を特定できるデータを適切に処理するために、追加のプライバシーとセキュリティ対策を採用しています。 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft マネージド デスクトップストレージとスタッフの場所

Microsoft マネージド デスクトップデータは、米国の Azure データ センターに格納されます。 サービスの運用を維持するにはMicrosoft マネージド デスクトップその他のサービスによって取得される個人データが必要です。 Microsoft マネージド デスクトップ からデバイスが削除された場合、Microsoft Defender for Endpoint によって収集されたアラート データを除き、最大 30 日間、セキュリティのために 180 日間保存される個人データを保持します。 データ保持の詳細については、「データの保持、削除、およびデータの破棄」を参照[Microsoft 365。](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)

Microsoft マネージド デスクトップエンジニアリング運用チームとセキュリティ運用チームは、米国とインドに位置しています。 

### <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10診断データ

Microsoft マネージド デスクトップは、Windows 10[診断](/windows/privacy/windows-diagnostic-data)データを使用して、セキュリティWindows最新の状態に保ち、問題のトラブルシューティングを行い、製品の改善を行います。 拡張診断データの設定には、Microsoft マネージド デスクトップに登録されているデバイスとその設定、機能、およびデバイスの正常性に関する詳細情報が含まれています。 拡張診断データを選択すると、必要な診断データを含むデータが収集されます。 診断[データの設定とWindowsの](/windows/privacy/changes-to-windows-diagnostic-data-collection)詳細については、「診断データコレクションの変更Windows 10変更」を参照してください。

診断データの用語は、将来のバージョンのバージョンで変更Windows。 Microsoft マネージド デスクトップは、サービスに必要なデータのみを処理するためにコミットされます。 これは、診断レベルが **Optional** に変わることを意味しますが、Microsoft マネージド デスクトップ は、サービスに必要な診断データ収集を微調整するための限られた診断ポリシーを実装します。 詳細については、「診断データ収集[の変更点Windows」を参照してください](/windows/privacy/changes-to-windows-diagnostic-data-collection)。

Microsoft マネージド デスクトップ、アプリケーション、デバイスの信頼性、パフォーマンス情報など、登録済みデバイスから発生する Windows 10 オプションの診断データからのシステム レベルのデータのみを処理および保存します。 Microsoft マネージド デスクトップ、チャットやブラウザーの履歴、音声、テキスト、音声などの顧客の個人データを処理および保存する必要があります。 

Microsoft Windows 10 の診断データコレクションの詳細については、「Microsoft Privacy Statement」の「個人データの保存と処理」セクションを参照してください。 [](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)

### <a name="microsoft-windows-update-for-business"></a>Microsoft Windowsビジネス向け更新プログラム
Microsoft Windows Update for Business は、更新プログラムのWindowsの状態とエラーを分析するために、ユーザー診断からのデータを使用します。 Microsoft マネージド デスクトップデータを活用し、このデータを使用して問題の軽減と解決を行い、登録済みのすべてのデバイスが定義済みの更新のケイデンスに基づいて最新の情報に更新されます。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Microsoft マネージド デスクトップ で使用されるデータの識別は、Azure Active Directory (Azure AD) によって、企業向け Microsoft Apps や Azure などの Microsoft オンライン サービスを購読する際に組織が提供する場所に基づいて地理的な場所に格納されます。 Microsoft マネージド デスクトップ で使用されるデータの識別は、企業向け Microsoft Apps や Azure などの Microsoft オンライン サービスを購読する際に組織が提供する場所に基づいて、Azure AD によって地理的な場所に格納されます。 Azure データの場所AD詳細については、「Azure Active Directory [- データの場所」を参照してください。](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intuneおよびサービスをサポートするために、データを収集、処理Microsoft マネージド デスクトップ共有します。 Intune [で収集されるデータの詳細については、「Intune](/mem/intune/protect/privacy-data-collect) でのデータ収集」を参照してください。 

データの場所の詳細Microsoft Intune、顧客データの保存場所[Microsoft 365を参照してください](/microsoft-365/enterprise/o365-data-locations)。 Intune は、管理者が顧客データに対して行った保存場所の選択を尊重します。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint
Microsoft Defender for Endpoint は、管理、追跡、およびレポートの目的で、Microsoft マネージド デスクトップデバイスの情報を収集および保存します。 収集される情報には、ファイル データ (ファイル名、サイズ、ハッシュなど)、プロセス データ (実行中のプロセス、ハッシュ)、レジストリ データ、ネットワーク接続データ、デバイスの詳細 (デバイス識別子、デバイス名、オペレーティング システムのバージョンなど) が含まれます。 [Microsoft Defender for Endpoint のデータ](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)収集とストレージの場所の詳細については、「Microsoft Defender for Endpoint data storage and privacy」を参照してください。 

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise 
Microsoft 365 Apps for enterpriseは、Microsoft マネージド デスクトップ Microsoft マネージド デスクトップ によって管理される定義済みの更新チャネルに基づいて、これらのアプリが最新バージョンで最新のバージョンに更新されるのを確認するために、Microsoft マネージド デスクトップ とデータを収集および共有します。 Microsoft [Defender for Endpoint のデータストレージとプライバシーを参照](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)して、Microsoft 365 Appsのデータ収集と保存場所の詳細について説明します。

## <a name="major-data-change-notification"></a>メジャー データ変更通知
Microsoft マネージド デスクトップ、サービス通信フレームワークで説明されている変更管理プロセスに従います。 セキュリティ インシデントとサービスMicrosoft 365変更Microsoft マネージド デスクトップ管理ポータルを通じて、お客様に通知します。 収集されたデータの種類と格納場所に対する変更は、重要な変更と見なされます。 この変更に関する詳細な通知は、製品およびサービスの標準的な方法と同様に、少なくとも 30 日間Microsoft 365提供します。 詳細については、「サービスの変更 [と通信」を参照してください](/microsoft-365/managed-desktop/service-description/servicechanges)。

## <a name="compliance"></a>コンプライアンス
Microsoft マネージド デスクトップ外部監査を受け、包括的なコンプライアンス提供のセットを取得しました。 詳細については、「コンプライアンス」Microsoft マネージド デスクトップ[参照してください](/microsoft-365/managed-desktop/intro/compliance)。 監査レポートは、Microsoft サービスセキュリティポータルでダウンロードできます。これは、Microsoft[サービス](https://aka.ms/stp)オンライン サービスのEnterprise機能します。 (Microsoft マネージド デスクトップ"監視と管理"というカテゴリの下に、これらのドキュメント内に一覧表示されます。

### <a name="data-subject-requests"></a>データ主体要求
Microsoft マネージド デスクトップ、GDPR および CCPA のプライバシー規制に従い、データ主体は個人データに対する特定の権利を与えます。 これらの権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、または別のコントローラーに移動するための電子形式での受信が含まれます。 データ主体要求 (DSR) の一般的な詳細については、「データ主体要求」および [「GDPR および CCPA」を参照してください](/compliance/regulatory/gdpr-data-subject-requests)。

ケース管理システムによって収集されたデータに関するデータ主体要求を実行するにはMicrosoft マネージド デスクトップを参照してください。

- Microsoft Defender for Endpoint アラートのデータ: セキュリティ管理者は、管理ポータルでレポート要求を送信することで、Microsoft Defender for Endpoint アラートに関連する個人データの削除または抽出を [要求できます](https://aka.ms/memadmin)。 要求で、[要求の変更] 、 **カテゴリ [** セキュリティ]、および **[その** 他] のサブカテゴリを選択 **します**。 要求の説明に関連するデバイス名を指定します。
- サポート要求Microsoft マネージド デスクトップデータ: IT 管理者は、管理者ポータルでレポート要求を送信することで、個人データ関連のサポート要求の削除または抽出を[要求できます](https://aka.ms/memadmin)。 要求で、[要求の変更] 、 **カテゴリ [** セキュリティ]、および **[その** 他] のサブカテゴリを選択 **します**。 要求の説明に関連するデバイス名またはユーザー名を指定します。

サービスに関連する他の製品の DSRs については、次の記事を参照してください。

- Windows[診断データ](/compliance/regulatory/gdpr-dsr-windows)
- Microsoft [Intune データ](/compliance/regulatory/gdpr-dsr-intune)
- Azure Active [Directory データ](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>法務
組織のお客様が提供する製品のエンド ユーザーに対する Microsoft [](https://privacy.microsoft.com/privacystatement)のプライバシーに関する通知 **-** Microsoft プライバシーステートメントは、エンド ユーザーが仕事用アカウントを使用して Microsoft 製品にサインインするときに、自分のアカウント (プライバシー関連の設定の制御を含む) を制御および管理し、データにアクセスして処理できるとエンド ユーザーに通知します。b) Microsoft は、データを収集および処理して、組織およびエンド ユーザーにサービスを提供する場合があります。
