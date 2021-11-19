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
description: アクティビティ エクスプローラーで使用できるラベル付けアクティビティの一覧。
ms.openlocfilehash: feed9d29deb94263d242967bdef38209cda660e1
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111425"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>アクティビティ エクスプローラーで利用可能なラベル付けアクティビティ

## <a name="sensitivity-label-applied"></a>秘密度ラベルを適用済み

このイベントは、ラベルの付いていないドキュメントにラベルが付けられたり、秘密度ラベルの付いたメールが送信されたりするたびに生成されます。

- Office のネイティブ アプリケーションや Web アプリケーションの保存時にキャプチャされます。
- Azure Information Protection アドインでの発生時にキャプチャされます。
- アップグレードおよびダウングレード ラベル アクションは、*[ラベル イベントの種類]* フィールドとフィルタを介して監視することもできます。

|ソース  |アクティビティ エクスプローラーで報告 | 注:  |
|---------|---------|---------|
| Word、Excel、PowerPoint|はい |
|Outlook| はい | |
|SharePoint Online、OneDrive|はい | |
|Exchange        |はい         | |
|Azure Information Protection (AIP) 統合クライアントと AIP 統合スキャナー |はい |AIP 新しい *ラベル アクション* は、アクティビティ エクスプローラー *で適用されるラベル* にマップされます。   |
|Microsoft 情報保護 (MIP) SDK         |はい|AIP 新しい *ラベル アクション* は、アクティビティ エクスプローラー *で適用されるラベル* にマップされます。|
|Rights Management サービス (RMS)         |該当なし         | |
|Power BI デスクトップと Web        | いいえ| 監査ログMicrosoft 365アクセス可能         |
|Microsoft Defender for Cloud Apps         |いいえ|         |

## <a name="sensitivity-label-changed"></a>秘密度ラベルを変更済み

このイベントは、ドキュメントやメールで秘密度ラベルが更新されるたびに生成されます。

- AIP Unified クライアント、Unified Scanner、MIP SDK ソースの場合 *、AIP* アップグレード ラベルとダウングレード ラベル アクションはアクティビティ エクスプローラー ラベルに *マップされます*。 

- Office のネイティブ アプリケーションや Web アプリケーションの保存時点でキャプチャされます。
- Azure Information Protection 統合クライアント アドインおよびスキャナー強化での発生時にキャプチャされます。
- アップグレードおよびダウングレード ラベル アクションは、*[ラベル イベントの種類]* フィールドとフィルタを介して監視することもできます。 SharePoint Online と OneDrive を除いた *理由* テキストもキャプチャされます。
- Outlook の Office ネイティブ アプリで行われる秘密度ラベルのラベル付けは、ファイル保存またはメール送信アクションの前に生成された最後の処理を収集します。 たとえば、送信前にユーザーがメールのラベルを複数回変更した場合、電子メールの送信時に最後に見つかったラベルは監査ログに記録され、アクティビティ エクスプローラーで報告されます。

|ソース  |アクティビティ エクスプローラーで報告|注:  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |はい         |
|Outlook         |はい         |
|SharePoint Online、OneDrive         |はい         |
|Exchange         |はい         |
|AIP 統合クライアント         |はい         |
|AIP 統合スキャナー         |はい         |
|MIP SDK         |はい         |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |いいえ         |監査ログMicrosoft 365アクセス可能 |
|Microsoft Defender for Cloud Apps     |いいえ         |         |

## <a name="sensitivity-label-removed"></a>秘密度ラベルを削除しました

このイベントは、ファイルやドキュメントから秘密度ラベルが削除されるたびに生成されます。

- このイベントは、Office のネイティブ アプリケーションや Web アプリケーションの保存時にキャプチャされます。
- Azure Information Protection アドインでの発生時にキャプチャされます。
- Outlook で Office ネイティブ MIP ラベルを使用した秘密度ラベルのラベル付けは、ファイル保存またはメール送信アクションの前に生成された最後のラベル付けイベントを収集します。

|ソース  |アクティビティ エクスプローラーで報告 | 注:  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |はい         |
|Outlook         |はい         ||
|SharePoint Online、OneDrive         |はい         |
|Exchange         |はい         |
|AIP 統合クライアント         |はい         |AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除* アクションにマップされます。|
|AIP 統合スキャナー         |はい         |AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除* アクションにマップされます。 |
|MIP SDK         |はい         |AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除* アクションにマップされます。 |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |いいえ         |監査ログMicrosoft 365アクセス可能 |
|Microsoft Defender for Cloud Apps     |いいえ         |         |

## <a name="sensitivity-label-file-read"></a>秘密度ラベル ファイルの読み取り

このイベントは、秘密度ラベルのラベル付けや保護されたドキュメントを開くたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告 | 注:  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |はい         |
|Outlook         |いいえ         |
|SharePoint Online、OneDrive         |いいえ         |
|Exchange         |いいえ         |
|AIP 統合クライアント         |はい         |AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。|
|AIP 統合スキャナー         |はい         |AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。|
|MIP SDK         |はい         |AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。|
|RMS サービス         |はい         |アクセス *アクションは* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。 |
|Power BI デスクトップと Web         |いいえ         |監査ログMicrosoft 365アクセス可能 |
|Microsoft Defender for Cloud Apps     |いいえ         |         |

## <a name="files-discovered"></a>検出されたファイル

このイベントは、AIP スキャナーを使用してさまざまな場所にある機密性の高いデータをスキャンしファイルを検索した場合に、ファイルが検出されるたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告 | 注:  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |該当なし         |
|Outlook         |該当なし         |
|SharePoint Online、OneDrive         |該当なし         |
|Exchange         |該当なし         |
|AIP 統合クライアント         |該当なし       |
|AIP 統合スキャナー         |はい         |AIP検出アクションは、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。|
|MIP SDK         |はい         |AIP 検出 *アクションは* 、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。|
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし         |
|Microsoft Defender for Cloud Apps     |該当なし         |         |

## <a name="sensitivity-label-file-renamed"></a>名前が変更された秘密度ラベル ファイル

このイベントは、秘密度ラベルの付いたドキュメントの名前が変更されるたびに生成されます。

|ソース  | アクティビティ エクスプローラーで報告 | 注:  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |はい         |
|Outlook         |該当なし         |
|SharePoint Online、OneDrive         |いいえ        |
|Exchange         |該当なし         |
|AIP 統合クライアント         |いいえ         |
|AIP 統合スキャナー         |いいえ         |
|MIP SDK         |いいえ         |
|RMS サービス         |いいえ      |
|Power BI デスクトップと Web         |いいえ         |
|Microsoft Defender for Cloud Apps     |いいえ         |         |

## <a name="file-removed"></a>ファイルが削除されました

このイベントは、以前にスキャンされたファイルが削除されたことを AIP スキャナーが検出するたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告 | 注:  |
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
|Microsoft Defender for Cloud Apps     |該当なし        |         |

### <a name="protection-applied"></a>保護を適用しました

このイベントは、ラベル付けされていないアイテムに初めて手動で保護機能を追加した場合に生成されます。

|ソース  |アクティビティ エクスプローラーで報告 | 注:  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |いいえ         |
|Outlook         |いいえ         |
|SharePoint Online、OneDrive         |該当なし           |
|Exchange         |いいえ       |
|AIP 統合クライアント         |はい            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |はい            |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし            |
|Microsoft Defender for Cloud Apps     |該当なし        |         |

## <a name="protection-changed"></a>保護を変更しました

このイベントは、ラベル付けされていないドキュメントの保護機能が手動で変更されるたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告 |
|---------|---------|
|Word、Excel、PowerPoint         |いいえ         |
|Outlook         |いいえ         |
|SharePoint Online、OneDrive         |該当なし           |
|Exchange         |いいえ       |
|AIP 統合クライアント         |はい            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |はい            |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし            |
|Microsoft Defender for Cloud Apps     |該当なし        |

## <a name="protection-removed"></a>保護を削除しました

このイベントは、ラベル付けされていないドキュメントの保護機能が手動で変更されるたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告 |
|---------|---------|
|Word、Excel、PowerPoint         |いいえ         |
|Outlook         |いいえ         |
|SharePoint Online、OneDrive         |該当なし           |
|Exchange         |いいえ       |
|AIP 統合クライアント         |はい            |
|AIP 統合スキャナー         |該当なし         |
|MIP SDK         |はい            |
|RMS サービス         |該当なし         |
|Power BI デスクトップと Web         |該当なし            |
|Microsoft Defender for Cloud Apps     |該当なし        |

## <a name="dlp-policy-matched"></a>DLP ポリシーの一致

このイベントは、DLP ポリシーがドキュメントやメールに一致するたびに生成されます。

|ソース  |アクティビティ エクスプローラーで報告 |
|---------|---------|
|Exchange         |はい       |
|SharePoint Online|はい          |
|OneDrive |はい|
|Teams |はい   |
|Windows 10 デバイス         |はい |
|MAC         |いいえ     |
|オンプレミス         |いいえ|
|Microsoft Defender for Cloud Apps     |いいえ        |

Windows 10 デバイス (エンドポイント DLP) のイベント:

- ファイルの削除
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

|ソース  |アクティビティ エクスプローラーで報告 |
|---------|---------|
|Exchange         |いいえ       |
|SharePoint Online|はい          |
|OneDrive |はい|

## <a name="retention-label-changed"></a>保持ラベルを変更しました

このイベントは、ドキュメントやメールでラベルが更新されるたびに生成されます。

- ドキュメントの場合は保存時に、メールの場合は送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告 |
|---------|---------|
|Exchange         |いいえ       |
|SharePoint Online|はい          |
|OneDrive |はい|

## <a name="retention-label-removed"></a>保持ラベルを削除しました

このイベントは、ファイルやドキュメントからラベルが削除されるたびに生成されます。

- ドキュメントの場合は保存時に、メールの場合は送信時にキャプチャされます。

|ソース  |アクティビティ エクスプローラーで報告 |
|---------|---------|
|Exchange         |いいえ       |
|SharePoint Online|はい          |
|OneDrive |はい|

## <a name="known-issues"></a>既知の問題
  
- 推奨ラベルのツール ヒントがエンド ユーザーに表示されても、それはキャプチャされません。 ただし、ユーザーが推奨ラベルの適用を選択した場合、ラベルは [適用方法] フィールドに [推奨]*として表示**されます*。

- 現在、SharePoint および OneDrive からの秘密度ラベルのダウングレードでは、理由テキストは利用できません。

- 現在、Word、Excel、PowerPoint、Outlook、SharePoint Online、OneDrive の自動ラベル付けアクティビティでは、機密情報の種類は利用できません。
