---
title: Office 365 Advanced Threat Protection のレポートを表示する
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターで Office 365 Advanced Threat Protection のレポートを検索して使用する方法について説明します。
ms.openlocfilehash: 9ad177e96184913be61e098a1aafa294a123199b
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866409"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection のレポートを表示する

組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) があり、[必要なアクセス許可](#what-permissions-are-needed-to-view-the-atp-reports)がある場合は、セキュリティ&amp;コンプライアンスセンターでいくつかの ATP レポートを使用できます。 ([**レポート** \> ]**ダッシュボード**に移動します。)
  
![セキュリティ&amp;コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP レポートには次のものが含まれます。
- [脅威保護の状態レポート](#threat-protection-status-report)
- [ATP ファイルの種類レポート](#atp-file-types-report)
- [ATP メッセージの廃棄レポート](#atp-message-disposition-report)
- [リアルタイム検出またはエクスプローラー](threat-explorer.md) (OFFICE 365 ATP プラン1または2を使用しているかどうかによって異なります)
- ...その[他](#additional-reports-to-view)。 

ATP レポートの概要とその使用方法については、この記事を参照してください。
  
## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) および[Office 365 ATP](office-365-atp.md)によって検出されブロックされます。 このレポートは、時間の経過による検出 (最大90日間) を表示するのに役立ち、セキュリティ管理者が傾向を特定したり、ポリシーが調整を必要とするかどうかを判断したりできます。 

脅威保護の状態レポートでは、マルウェア対策エンジンによってブロックされたファイルや web サイトアドレス (Url)、[ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)、Atp の[安全](atp-safe-links.md)な[添付ファイル](atp-safe-attachments.md)、atp の[フィッシング対策機能](atp-anti-phishing.md)などの atp 機能など、悪意のあるコンテンツを含む一意の電子メールメッセージの集計数が提供されます。 

> [!NOTE]
> 脅威保護の状態レポートは、 [Office 365 ATP](office-365-atp.md)または[Exchange Online Protection](exchange-online-protection-eop.md) (EOP) のいずれかを使用しているお客様が利用できます。ただし、ATP のお客様の脅威保護状態レポートに表示される情報には、EOP のお客様に表示されるものとは異なるデータが含まれている可能性があります。 たとえば、ATP のお客様向けの脅威保護状態レポートには、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報が含まれています。 このような情報は ATP に固有のものなので、EOP を持たないお客様は脅威保護の状態レポートにこれらの詳細を表示しません。
  
脅威保護の状態レポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \>の**脅威保護の状態**] に移動します。
  
![ATP の脅威保護状態レポート](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
1日の詳細な状態を取得するには、グラフの上にポインターを移動します。
  
![1日の ATP の脅威保護状態データ](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
既定では、脅威保護の状態レポートには過去7日間のデータが表示されます。 ただし、**フィルター**を選択し、日付の範囲を変更して、最大90日間のデータを表示することができます。 (試用版サブスクリプションを使用している場合は、30日間のデータに制限されることがあります)。
  
![ATP の脅威保護状態フィルター](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
[**データの表示**] メニューを使用して、レポートに表示される情報を変更することもできます。 
  
![ATP の脅威保護状態レポートの表示オプション](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>ATP ファイルの種類レポート

**Atp ファイルの種類**レポートには、 [atp の安全な添付](atp-safe-attachments.md)ファイルによって検出されたファイルの種類が表示されます。
  
このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP**] [ファイルの種類] に移動します。
  
![ATP ファイルの種類レポート](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
特定の日の上にカーソルを移動すると、 [Office 365 で&amp; ](anti-spam-and-anti-malware-protection.md)、ATP の安全な[添付](atp-safe-attachments.md)ファイルとスパム対策のマルウェア対策保護によって検出された悪意のあるファイルの種類の分類を確認できます。
  
![1日の ATP ファイルタイプレポートデータ](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP メッセージの廃棄レポート

**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。 
  
このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP メッセージ廃棄**] に移動します。
  
![ATP メッセージディスポジションレポート](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
グラフのバーの上にマウスカーソルを移動すると、その日に検出されたメールに対して実行されたアクションを確認できます。
  
![1日の ATP メッセージディスポジションレポートデータ](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>表示する追加レポート

この記事で説明されている ATP レポートに加えて、次の表に示すように、他にもいくつかのレポートを利用できます。

|レポート (s)  |詳細  |
|---------|---------|
|**エクスプローラー**または**リアルタイム検出**(Office 365 ATP Plan 2 のお客様はエクスプローラーを所有しています。Office 365 ATP Plan 1 お客様はリアルタイムの検出を行っています。| [脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)       |
|上位の送信者と受信者のレポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。 | [セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する](../../compliance/view-email-security-reports.md)        |
|**ATP の安全なリンク URL トレース**(PowerShell を使用して生成したレポート)このレポートには、過去7日間 (7 日間) の ATP の安全なリンクアクションの結果が表示されます。 |[取得-UrlTrace コマンドレットリファレンス](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|**EOP および ATP の結果**(PowerShell を使用して生成するカスタムレポート)。 このレポートには、ドメイン、日付、イベントの種類、方向、アクション、メッセージ数などの情報が含まれます。  | [Get-mailtrafficatpreport コマンドレットリファレンス](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|**EOP および ATP の検出**(PowerShell を使用して生成するカスタムレポート)。 このレポートには、悪意のあるファイルまたは Url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。   | [Get-MailDetailATPReport コマンドレットリファレンス](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>ATP レポートを表示するには、どのようなアクセス許可が必要ですか。

この記事に記載されているレポートを表示して使用するには、**セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。

- セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。
    - 組織の管理
    - セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)
    - セキュリティリーダ

- Exchange Online の場合は、Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [Exchange online Powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。
    - 組織の管理
    - 表示限定の組織管理
    - "View-Only Recipients/表示専用受信者" 役割
    - コンプライアンス管理

詳細については、次のリソースを参照してください。

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>レポートでデータが表示されない場合はどうなりますか。

ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。 組織で atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)と[atp の安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)が定義されている必要があります。これは、atp 保護を適切に実行するためです。 また、「[スパム対策およびマルウェア対策保護 (Office 365](anti-spam-and-anti-malware-protection.md))」を参照してください。
  
## <a name="related-topics"></a>関連項目

[Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報](reports-and-insights-in-security-and-compliance.md)
  
[セキュリティ&amp; /コンプライアンスセンターでレポートのスケジュールを作成する](create-a-schedule-for-a-report.md)
  
[セキュリティ&amp; /コンプライアンスセンターでカスタムレポートを設定およびダウンロードする](set-up-and-download-a-custom-report.md)
  

