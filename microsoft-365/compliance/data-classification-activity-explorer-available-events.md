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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: アクティビティ エクスプローラーで使用できるラベル付けアクティビティの一覧。
ms.openlocfilehash: 163231d4d1e7c6a2d1b75c0f81a17443cfafe246
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176008"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>アクティビティ エクスプローラーで使用できるアクティビティのラベル付け

## <a name="sensitivity-label-applied"></a>適用される感度ラベル

このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、電子メールが感度ラベル付きで送信されるごとに生成されます。 

- これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存時にキャプチャされます。 
- Azure Information Protection アドインで発生した時点でキャプチャされます。 
- ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。   


|ソース  |アクティビティ エクスプローラーで報告される | 注:  |
|---------|---------|---------|
| Word、Excel、PowerPoint|○ |
|Outlook| ○ | |
|SharePointオンライン、OneDrive|はい | |
|Exchange        |○         | |
|Azure Information Protection (AIP) 統合クライアントと AIP 統合スキャナー |○ |AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。   |
|Microsoft の情報保護 (MIP) SDK         |○|AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。|
|Rights Management Service (RMS)         |該当なし         | |
|Power BIと Web        | no| 監査ログでMicrosoft 365アクセス可能         |
|Microsoft Cloud App Security (MCAS)         |no|         |

## <a name="sensitivity-label-changed"></a>感度ラベルの変更

このイベントは、ドキュメントまたは電子メールで感度ラベルが更新されるごとに生成されます。

- AIP Unified クライアント、Unified Scanner、MIP SDK ソースの場合 *、AIP* アップグレード ラベルとダウングレード ラベル アクションはアクティビティ エクスプローラー ラベルに *マップされます*。 

- これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存の時点でキャプチャされます。 
- Azure Information Protection 統合クライアント アドインとスキャナーの適用で発生した時点でキャプチャされます。
- ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。 また *、位置合わせ* テキストは、[オンライン] および [SharePoint] 以外OneDrive。
- ファイルの保存/電子メール送信Office前にOutlookされた最後のアクションが収集されます。 たとえば、ユーザーが送信前にメールのラベルを複数回変更した場合、電子メールの送信時に最後に見つかったラベルは監査ログに記録され、アクティビティ エクスプローラーで報告されます。 


|ソース  |アクティビティ エクスプローラーで報告される|注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |○         |
|SharePointオンライン、OneDrive         |はい         |
|Exchange         |○         |
|AIP 統合クライアント         |○         |
|AIP 統合スキャナー         |○         |
|MIP SDK         |○         |
|RMS サービス         |該当なし         |
|Power BIと Web         |no         |監査ログでMicrosoft 365アクセス可能 |
|MCAS     |no         |         |

## <a name="sensitivity-label-removed"></a>[感度ラベルの削除]

このイベントは、ファイルまたはドキュメントから感度ラベルが削除されるごとに生成されます。

- このイベントは、ネイティブ アプリケーションおよび web アプリケーションOffice保存時にキャプチャされます。
- Azure Information Protection アドインで発生した時点でキャプチャされます。 
- Outlook では、Office MIP ラベルを使用して、ファイルの保存/電子メール送信アクションの前に生成された最後のラベル付けイベントを収集します。

|ソース  |アクティビティ エクスプローラーで報告される | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |○         ||
|SharePointオンライン、OneDrive         |はい         |
|Exchange         |○         |
|AIP 統合クライアント         |○         |AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。|
|AIP 統合スキャナー         |○         |AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。 |
|MIP SDK         |○         |AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。 |
|RMS サービス         |該当なし         |
|Power BIと Web         |no         |監査ログでMicrosoft 365アクセス可能 |
|MCAS     |no         |         |
 

## <a name="sensitivity-label-file-read"></a>感度ラベル ファイルの読み取り

このイベントは、ラベル付きまたは保護されたドキュメントが開く度に生成されます。

|ソース  |アクティビティ エクスプローラーで報告される | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |no         |
|SharePointオンライン、OneDrive         |no         |
|Exchange         |no         |
|AIP 統合クライアント         |○         |AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。|
|AIP 統合スキャナー         |○         |AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。|
|MIP SDK         |○         |AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。|
|RMS サービス         |○         |アクセス *アクションは* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。 |
|Power BIと Web         |no         |監査ログでMicrosoft 365アクセス可能 |
|MCAS     |no         |         |


## <a name="files-discovered"></a>検出されたファイル

このイベントは、AIP スキャナーを使用してさまざまな場所で機密データをスキャンし、ファイルを検索するときに、ファイルが検出される度に生成されます。

|ソース  |アクティビティ エクスプローラーで報告される | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |該当なし         |
|Outlook         |該当なし         |
|SharePointオンライン、OneDrive         |該当なし         |
|Exchange         |該当なし         |
|AIP 統合クライアント         |該当なし       |
|AIP 統合スキャナー         |○         |AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。|
|MIP SDK         |○         |AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。|
|RMS サービス         |該当なし         |
|Power BIと Web         |該当なし         |
|MCAS     |該当なし         |         |


## <a name="sensitivity-label-file-renamed"></a>名前が変更された感度ラベル ファイル

このイベントは、感度ラベルが付いたドキュメントの名前が変更される度に生成されます。 

|ソース  | アクティビティ エクスプローラーで報告される | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |○         |
|Outlook         |該当なし         |
|SharePointオンライン、OneDrive         |no        |
|Exchange         |該当なし         |
|AIP 統合クライアント         |no         |
|AIP 統合スキャナー         |no         |
|MIP SDK         |no         |
|RMS サービス         |no      |
|Power BIと Web         |no         |
|MCAS     |no         |         |


## <a name="file-removed"></a>削除されたファイル

このイベントは、AIP スキャナーが以前にスキャンしたファイルが削除されたと検出する度に生成されます。

|ソース  |アクティビティ エクスプローラーで報告される | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |該当なし         |
|Outlook         |該当なし         |
|SharePointオンライン、OneDrive         |該当なし           |
|Exchange         |該当なし         |
|AIP 統合クライアント         |該当なし            |
|AIP 統合スキャナー         |○         |
|MIP SDK         |該当なし            |
|RMS サービス         |該当なし         |
|Power BIと Web         |該当なし  |
|MCAS     |該当なし        |         |

### <a name="protection-applied"></a>適用される保護

このイベントは、ラベルを持つアイテムに手動で追加される初めての保護が生成されます。

|ソース  |アクティビティ エクスプローラーで報告される | 注:  |
|---------|---------|---------| 
|Word、Excel、PowerPoint         |no         |
|Outlook         |no         |
|SharePointオンライン、OneDrive         |該当なし           |
|Exchange         |no       |
|AIP 統合クライアント         |○            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |○            |
|RMS サービス         |該当なし         |
|Power BIと Web         |該当なし            |
|MCAS     |該当なし        |         |

## <a name="protection-changed"></a>保護の変更

このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。

|ソース  |アクティビティ エクスプローラーで報告される |
|---------|---------| 
|Word、Excel、PowerPoint         |no         |
|Outlook         |no         |
|SharePointオンライン、OneDrive         |該当なし           |
|Exchange         |no       |
|AIP 統合クライアント         |○            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |○            |
|RMS サービス         |該当なし         |
|Power BIと Web         |該当なし            |
|MCAS     |該当なし        |

## <a name="protection-removed"></a>保護が削除されました

このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。

|ソース  |アクティビティ エクスプローラーで報告される |
|---------|---------| 
|Word、Excel、PowerPoint         |no         |
|Outlook         |no         |
|SharePointオンライン、OneDrive         |該当なし           |
|Exchange         |no       |
|AIP 統合クライアント         |○            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |○            |
|RMS サービス         |該当なし         |
|Power BIと Web         |該当なし            |
|MCAS     |該当なし        |

## <a name="dlp-policy-matched"></a>DLP ポリシーの一致

このイベントは、ドキュメントまたは電子メールで DLP ポリシーが一致する度に生成されます。

|ソース  |アクティビティ エクスプローラーで報告される |
|---------|---------| 
|Exchange         |○       |
|SharePoint Online|○          |
|OneDrive |はい|
|Teams |○   |
|Windows 10 デバイス         |○ |
|MAC         |no     |
|オンプレミス         |no|
|MCAS     |no        | 

デバイス (エンドポイント DLP) Windows 10イベントは次のとおりです。

- ファイルが削除されました
- 作成されたファイル
- ファイルがクリップボードにコピーされました
- 変更されたファイル
- ファイルの読み取り
- ファイルが印刷されました
- ファイルの名前が変更されました
- ファイルがネットワーク共有にコピーされました
- 許可されていないアプリによってアクセスされるファイル


## <a name="retention-label-applied"></a>アイテム保持ラベルの適用 

このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、保持ラベル付きメールが送信されるごとに生成されます。

- ドキュメントの保存時と電子メールの送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告される |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|○          |
|OneDrive |○|

## <a name="retention-label-changed"></a>アイテム保持ラベルの変更

このイベントは、ドキュメントまたは電子メールでラベルが更新されるごとに生成されます。

- ドキュメントの保存時と電子メールの送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告される |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|○          |
|OneDrive |○|
 
## <a name="retention-label-removed"></a>アイテム保持ラベルの削除

このイベントは、ファイルまたはドキュメントからラベルが削除されるごとに生成されます。

- ドキュメントの保存時と電子メールの送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告される |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|○          |
|OneDrive |○|


## <a name="known-issues"></a>既知の問題
  
- 推奨ラベル ツール ヒントがエンド ユーザーに表示されている場合、そのヒントはキャプチャされません。 ただし、ユーザーが推奨ラベルの適用を選択した場合、ラベルは [適用方法] フィールドの下に [推奨]*として表示**されます。*  

- 位置合わせのテキストは、現在、感度ラベルのダウングレード時に、SharePointおよびOneDrive。  

- 現在、機密情報の種類は、Word、Excel、PowerPoint、Outlook、および SharePoint Online、および OneDrive からの自動ラベル付けアクティビティでは使用できません。
