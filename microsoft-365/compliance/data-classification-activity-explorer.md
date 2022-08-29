---
title: アクティビティ エクスプローラーの概要
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
description: アクティビティ エクスプローラーを使用すると、ラベル付きコンテンツに対してユーザーが実行しているアクションを表示およびフィルター処理できます。
ms.openlocfilehash: 06e77cf567c34f49da7206dd22f030ddb35e6b3d
ms.sourcegitcommit: d1f51dbd12ceffe6a6aeebffde0f9a744486f2d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67417392"
---
# <a name="get-started-with-activity-explorer"></a>アクティビティ エクスプローラーの使用を開始する

[データ分類の概要](data-classification-overview.md)と[コンテンツ エクスプローラー](data-classification-content-explorer.md)のタブを使用すると、検出およびラベル付けされたコンテンツとそのコンテンツの場所を確認できます。 アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。 アクティビティ エクスプローラーは、ラベル付けされたコンテンツに対するアクティビティの履歴ビューを提供します。 アクティビティ情報は、Microsoft 365 統合監査ログから収集され、変換され、アクティビティ エクスプローラー UI で使用できるようになります。 アクティビティ エクスプローラーでは、最大 30 日間分のデータが報告されます。

![プレースホルダースクリーンショットの概要アクティビティ エクスプローラー。](../media/data-classification-activity-explorer-1.png)

使用可能なフィルターは 30 種類以上あり、以下がその一例です。

- 日付範囲
- アクティビティの種類
- 場所
- User
- 機密ラベル
- 保持ラベル
- ファイル パス
- DLP ポリシー



## <a name="prerequisites"></a>前提条件

データ分類にアクセスして使用するすべてのアカウントには、これらのいずれかのサブスクリプションのライセンスが割り当てられている必要があります。

- Microsoft 365 (E5)
- Office 365 (E5)
- 高度なコンプライアンス (E5) アドオン
- 高度な脅威インテリジェンス (E5) アドオン
- Microsoft 365 E5/A5 情報保護およびガバナンス
- Microsoft 365 E5/A5 コンプライアンス

### <a name="permissions"></a>アクセス許可

アカウントには、これらのロール グループのいずれかでメンバーシップを明示的に割り当てるか、ロールを明示的に付与する必要があります。

### <a name="roles-and-role-groups"></a>ロールとロール グループ

アクセス制御を微調整するために使用できるロールと役割グループがあります。

使用できる適用可能なロールの一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)」を参照してください。

- Information Protection 管理者
- Information Protection アナリスト
- Information Protection 調査員
- Information Protection 閲覧者

使用できる該当する役割グループの一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割グループ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)」を参照してください。

- 情報保護
- Information Protection レベル
- Information Protection アナリスト
- Information Protection 調査担当者
- Information Protection 閲覧者

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Microsoft 365 の役割グループ**

- 全体管理者
- コンプライアンス管理者
- セキュリティ管理者
- コンプライアンス データ管理者

**Microsoft 365 ロール**

- コンプライアンス管理者
- セキュリティ管理者
- セキュリティ閲覧者

## <a name="activity-types"></a>アクティビティの種類

アクティビティ エクスプローラーは、アクティビティの複数のソースの監査ログからアクティビティ情報を収集します。 アクティビティ エクスプローラーに表示されるラベル付けアクティビティの詳細については、「アクティビティ エクスプローラー [で使用できるラベル付けイベント」を参照してください](data-classification-activity-explorer-available-events.md)。

Office ネイティブ アプリケーション、Azure Information Protection (AIP) 統合ラベル付けクライアントとスキャナー、SharePoint Online、Exchange Online (秘密度ラベルのみ)、OneDrive からの **機密ラベル アクティビティ** と **保持ラベル付けアクティビティ**。 次に例を示します。

- ラベルが適用されました
- ラベルが変更されました (アップグレード、ダウングレード、または削除されました)
- 自動ラベル付けシミュレーション
- ファイルの読み取り

**Azure Information Protection (AIP) スキャナーと AIP クライアント**

- 保護を適用しました
- 保護を変更しました
- 保護を削除しました
- 検出されたファイル

アクティビティ エクスプローラーでは、Exchange Online、SharePoint Online、OneDrive、Teams チャットとチャネル (プレビュー)、オンプレミスの SharePoint フォルダーとライブラリ、オンプレミスのファイル共有、および **エンドポイント データ損失防止 (DLP)** を介したWindows 10 デバイスからのイベントと **一致する DLP ポリシー** も収集されます。 Windows 10 デバイスからのイベントの例を次に示します。

- Deletions
- 作品
- クリップボードにコピー
- Modified
- 読み取り
- 印刷
- 変更
- ネットワーク共有にコピー済み
- 未承認のアプリからアクセスされる 

機密性の高いラベル付けされたコンテンツで実行されているアクションを理解すると、[Microsoft Purview データ損失防止](dlp-learn-about-dlp.md) ポリシーなどのコントロールが有効かどうかを確認できます。 そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。

> [!NOTE]
> アクティビティ エクスプローラーは現在、Exchange Online の保持アクティビティを監視していません。

## <a name="see-also"></a>関連項目

- [秘密度ラベルの詳細](sensitivity-labels.md)
- [アイテム保持ポリシーと保持ラベルの詳細](retention.md)
- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md)
- [データ分類の説明](data-classification-overview.md)
