---
title: アクティビティ エクスプローラーで報告されたラベル付けアクション
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: アクティビティ エクスプローラーで利用可能なラベル付けアクティビティの一覧表示。
ms.openlocfilehash: ed1b207f4d0879185d757e2481cc3e8879293710
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173477"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>アクティビティ エクスプローラーで利用可能なラベル付けアクティビティ

## <a name="sensitivity-label-applied"></a>秘密度ラベルを適用済み

このイベントは、ラベルの付いていないドキュメントにラベルが付けられたり、秘密度ラベルの付いたメールが送信されたりするたびに生成されます。 

- Office のネイティブ アプリケーションや Web アプリケーションの保存時にキャプチャされます。 
- Azure Information Protection アドインでの発生時にキャプチャされます。 
- アップグレードおよびダウングレード ラベル アクションは、*[ラベル イベントの種類]* フィールドとフィルタを介して監視することもできます。   


|ソース  |アクティビティ エクスプローラーで報告済み | 注:  |
|---------|---------|---------|
| Word、Excel、PowerPoint|はい |
|Outlook| ○ | |
|SharePoint Online、OneDrive|はい | |
|Exchange        |○         | |
|Azure Information Protection (AIP) 統合クライアントと AIP 統合スキャナー |○ |AIP *新規ラベル* アクションは、アクティビティ エクスプローラーの *適用されたラベル* にマップされています。   |
|Microsoft 情報保護 (MIP) SDK         |○|AIP *新規ラベル* アクションは、アクティビティ エクスプローラーの *適用されたラベル* にマップされています。|
|Rights Management サービス (RMS)         |該当なし         | |
|Power BI デスクトップと Web        | no| Microsoft 365 監査ログにアクセス可能         |
|Microsoft Cloud App Security (MCAS)         |no|         |

## <a name="sensitivity-label-changed"></a>秘密度ラベルを変更済み

このイベントは、ドキュメントやメールで秘密度ラベルが更新されるたびに生成されます。

- AIP 統合クライアント、統合スキャナー、MIP SDK ソースでは、AIP *アップグレード ラベル* および *ダウングレード ラベル* アクションがアクティビティ エクスプローラー *ラベル変更済み* にマップされます。

- Office のネイティブ アプリケーションや Web アプリケーションの保存時点でキャプチャされます。 
- Azure Information Protection 統合クライアント アドインおよびスキャナー強化での発生時にキャプチャされます。
- アップグレードおよびダウングレード ラベル アクションは、*[ラベル イベントの種類]* フィールドとフィルタを介して監視することもできます。 SharePoint Online と OneDrive を除いた *理由* テキストもキャプチャされます。
- Outlook の Office ネイティブ アプリで行われる秘密度ラベルのラベル付けは、ファイル保存またはメール送信アクションの前に生成された最後の処理を収集します。 たとえば、ユーザーがメール送信前にラベルを複数回変更した場合、送信時にメールで検出された最後のラベルが監査ログにキャプチャされ、アクティビティ エクスプローラーで報告されます。 


|ソース  |アクティビティ エクスプローラーで報告済み|注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |○         |
|SharePoint Online、OneDrive         |はい         |
|Exchange         |○         |
|AIP 統合クライアント         |○         |
|AIP 統合スキャナー         |はい         |
|MIP SDK         |○         |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |no         |Microsoft 365 監査ログにアクセス可能 |
|MCAS     |no         |         |

## <a name="sensitivity-label-removed"></a>秘密度ラベルを削除しました

このイベントは、ファイルやドキュメントから秘密度ラベルが削除されるたびに生成されます。

- このイベントは、Office のネイティブ アプリケーションや Web アプリケーションの保存時にキャプチャされます。
- Azure Information Protection アドインでの発生時にキャプチャされます。 
- Outlook で Office ネイティブ MIP ラベルを使用した秘密度ラベルのラベル付けは、ファイル保存またはメール送信アクションの前に生成された最後のラベル付けイベントを収集します。

|ソース  |アクティビティ エクスプローラーで報告済み | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |○         ||
|SharePoint Online、OneDrive         |はい         |
|Exchange         |○         |
|AIP 統合クライアント         |○         |AIP の *ラベルの削除* アクションは、アクティビティ エクスプローラーの *削除済みラベル* アクションにマップされます。|
|AIP 統合スキャナー         |○         |AIP の *ラベルの削除* アクションは、アクティビティ エクスプローラーの *削除済みラベル* アクションにマップされます。 |
|MIP SDK         |○         |AIP の *ラベルの削除* アクションは、アクティビティ エクスプローラーの *削除済みラベル* アクションにマップされます。 |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |no         |Microsoft 365 監査ログにアクセス可能 |
|MCAS     |no         |         |
 

## <a name="sensitivity-label-file-read"></a>秘密度ラベル ファイルの読み取り

このイベントは、秘密度ラベルのラベル付けや保護されたドキュメントを開くたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告済み | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |no         |
|SharePoint Online、OneDrive         |no         |
|Exchange         |no         |
|AIP 統合クライアント         |はい         |AIP の *アクセス* アクションは、アクティビティ エクスプローラーの *ファイルの読み取り* アクションにマップされます。|
|AIP 統合スキャナー         |○         |AIP の *アクセス* アクションは、アクティビティ エクスプローラーの *ファイルの読み取り* アクションにマップされます。|
|MIP SDK         |○         |AIP の *アクセス* アクションは、アクティビティ エクスプローラーの *ファイルの読み取り* アクションにマップされます。|
|RMS サービス         |はい         |*アクセス* アクションは、アクティビティ エクスプローラーの *ファイルの読み取り* アクションにマップされます。 |
|Power BI デスクトップと Web         |no         |Microsoft 365 監査ログにアクセス可能 |
|MCAS     |no         |         |


## <a name="files-discovered"></a>検出されたファイル

このイベントは、AIP スキャナーを使用してさまざまな場所にある機密性の高いデータをスキャンしファイルを検索した場合に、ファイルが検出されるたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告済み | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |該当なし         |
|Outlook         |該当なし         |
|SharePoint Online、OneDrive         |該当なし         |
|Exchange         |該当なし         |
|AIP 統合クライアント         |該当なし       |
|AIP 統合スキャナー         |○         |AIP の *検出* アクションは、アクティビティ エクスプローラーの *ファイルの検出* アクションにマップされます。|
|MIP SDK         |○         |AIP の *検出* アクションは、アクティビティ エクスプローラーの *ファイルの検出* アクションにマップされます。|
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし         |
|MCAS     |該当なし         |         |


## <a name="sensitivity-label-file-renamed"></a>名前が変更された秘密度ラベル ファイル

このイベントは、秘密度ラベルの付いたドキュメントの名前が変更されるたびに生成されます。 

|ソース  | アクティビティ エクスプローラーで報告済み | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |該当なし         |
|SharePoint Online、OneDrive         |no        |
|Exchange         |該当なし         |
|AIP 統合クライアント         |no         |
|AIP 統合スキャナー         |no         |
|MIP SDK         |no         |
|RMS サービス         |no      |
|Power BI デスクトップと Web         |no         |
|MCAS     |no         |         |


## <a name="file-removed"></a>ファイルが削除されました

このイベントは、以前にスキャンされたファイルが削除されたことを AIP スキャナーが検出するたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告済み | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |該当なし         |
|Outlook         |該当なし         |
|SharePoint Online、OneDrive         |該当なし           |
|Exchange         |該当なし         |
|AIP 統合クライアント         |該当なし            |
|AIP 統合スキャナー         |はい         |
|MIP SDK         |該当なし            |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし  |
|MCAS     |該当なし        |         |

### <a name="protection-applied"></a>保護を適用しました

このイベントは、ラベル付けされていないアイテムに初めて手動で保護機能を追加した場合に生成されます。

|ソース  |アクティビティ エクスプローラーで報告済み | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |no         |
|Outlook         |no         |
|SharePoint Online、OneDrive         |該当なし           |
|Exchange         |no       |
|AIP 統合クライアント         |○            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |○            |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし            |
|MCAS     |該当なし        |         |

## <a name="protection-changed"></a>保護を変更しました

このイベントは、ラベル付けされていないドキュメントの保護機能が手動で変更されるたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告済み |
|---------|---------| 
|Word、Excel、PowerPoint         |no         |
|Outlook         |no         |
|SharePoint Online、OneDrive         |該当なし           |
|Exchange         |no       |
|AIP 統合クライアント         |はい            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |○            |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし            |
|MCAS     |該当なし        |

## <a name="protection-removed"></a>保護を削除しました

このイベントは、ラベル付けされていないドキュメントの保護機能が手動で変更されるたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告済み |
|---------|---------| 
|Word、Excel、PowerPoint         |no         |
|Outlook         |no         |
|SharePoint Online、OneDrive         |該当なし           |
|Exchange         |no       |
|AIP 統合クライアント         |はい            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |はい            |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし            |
|MCAS     |該当なし        |

## <a name="dlp-policy-matched"></a>DLP ポリシーの一致

このイベントは、DLP ポリシーがドキュメントやメールに一致するたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告済み |
|---------|---------| 
|Exchange         |○       |
|SharePoint Online|○          |
|OneDrive |はい|
|Teams |はい   |
|Windows 10 デバイス         |○ |
|MAC         |no     |
|オンプレミス         |no|
|MCAS     |no        | 

Windows 10 デバイス (エンドポイント DLP) のイベント:

- ファイルが削除されました
- ファイルが作成されました
- ファイルがクリップボードにコピーされました
- ファイルが変更されました
- ファイルの読み取り
- ファイルが印刷されました
- ファイルの名前が変更されました
- ファイルがネットワーク共有にコピーされました
- ファイルが許可されていないアプリによってアクセスされました


## <a name="retention-label-applied"></a>保持ラベルを適用済み 

このイベントは、ラベルの付いていないドキュメントにラベルが付けられたり、保持ラベルの付いたメールが送信されたりするたびに生成されます。

- ドキュメントの場合は保存時に、メールの場合は送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告済み |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|○          |
|OneDrive |○|

## <a name="retention-label-changed"></a>保持ラベルを変更しました

このイベントは、ドキュメントやメールでラベルが更新されるたびに生成されます。

- ドキュメントの場合は保存時に、メールの場合は送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告済み |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|○          |
|OneDrive |○|
 
## <a name="retention-label-removed"></a>保持ラベルを削除しました

このイベントは、ファイルやドキュメントからラベルが削除されるたびに生成されます。

- ドキュメントの場合は保存時に、メールの場合は送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告済み |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|○          |
|OneDrive |○|


## <a name="known-issues"></a>既知の問題
  
- 推奨ラベルのツール ヒントがエンド ユーザーに表示されても、それはキャプチャされません。 ただし、ユーザーが推奨ラベルの適用を選択した場合、そのラベルは *適用方法* フィールドの下に *推奨* として表示されます。  

- 現在、SharePoint および OneDrive からの秘密度ラベルのダウングレードでは、理由テキストは利用できません。  

- 現在、Word、Excel、PowerPoint、Outlook、SharePoint Online、OneDrive の自動ラベル付けアクティビティでは、機密情報の種類は利用できません。
