---
title: 管理者による提出、提出、スパムの問題、誤検出、フィッシング、スキャン用電子メールの送信、Office 365 での疑わしい電子メールの送信、メールをスキャンする、フィッシングの Microsoft スキャンを実行する、電子メールを送信する、電子メールを送信する、電子メールを送信する、電子メールを送信する、電子メールを送信する、電子メールを送信する、microsoft に悪意のある、メール内のマルウェアを Microsoft に報告する、受信トレイにスパム電子メールを送信する、電子メールをウイルスに報告する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 疑わしいメール、疑わしいフィッシングメール、スパム、およびその他の潜在的に有害なメッセージ、Url、およびその他の潜在的な問題がある電子メールをスキャンのために社内から Microsoft に送信する方法について説明します。
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631383"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する

Exchange Online のメールボックスを使用する Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンスセンターの送信ポータルを使用して、電子メールメッセージ、Url、添付ファイルをスキャン用に Microsoft に提出することができます。

電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。 メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。

その他の方法で、電子メールメッセージ、Url、添付ファイルを Microsoft に提出する方法については、 

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **送信**ページに直接移動するには、 <https://protection.office.com/reportsubmission>を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 スパム対策ポリシーを追加、変更、および削除するには、**組織の管理**、**セキュリティ管理者**、または**セキュリティリーダー**の役割グループのメンバーである必要があります。 セキュリティ & コンプライアンスセンターの役割グループの詳細については、「[セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- ユーザーがメッセージやファイルを Microsoft に送信する方法の詳細については、「 [microsoft にレポートメッセージとファイルを](report-junk-email-messages-to-microsoft.md)送信する」を参照してください。

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a>疑わしいコンテンツを Microsoft のスキャンに送信する方法

Microsoft にコンテンツを送信するには、送信ページの左上にある [**新しい送信**] ボタンをクリックします。 ページの右側にあるポップアップが表示され、電子メール、URL、またはファイルのいずれかを送信するオプションが表示されます。

### <a name="submit-a-questionable-email-to-microsoft"></a>疑わしいメールを Microsoft に送信する

![電子メール送信の例](../../media/submission-flyout-email.PNG)

1. 電子メールを送信するには、[**電子**メール] を選択し、電子メール**ネットワークのメッセージ ID**を指定するか、電子メールファイルをアップロードします。

2. ポリシーチェックの実行対象となる受信者を指定します。 ポリシーチェックは、ユーザーまたはテナントレベルのポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。

3. 電子メールがブロックされているかどうかを指定します。 メールがブロックされている必要がある場合は、スパム、フィッシング、またはマルウェアとしてブロックされているかどうかを指定します。 可能な種類がわからない場合は、最適な判断を行ってください。

   - 送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。

   - 1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。 [状態] リンクをクリックすると、送信に関する追加情報が表示されます。 これには、ポリシーチェックの結果と rescan verdict が含まれます。 メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。

4. [**送信**] ボタンをクリックします。

### <a name="send-a-suspect-url-to-microsoft"></a>疑わしい URL を Microsoft に送信する

![電子メール送信の例](../../media/submission-url-flyout.png)

1. URL を送信するには、ポップアップから [ **url** ] を選択します。 プロトコル (**https://**) を含む完全な URL を入力します。

   [**フィルター済み**] を選択した場合は、URL がフィッシングまたはマルウェアであるかどうかを指定します。

2. [**送信**] ボタンをクリックします。

### <a name="submit-a-suspected-file-to-microsoft"></a>疑わしいファイルを Microsoft に送信する

![電子メール送信の例](../../media/submission-file-flyout.PNG)

1. ファイルを送信するには、ポップアップ**からファイルを選択し**、スキャンしたいファイルをアップロードします。

2. [**送信**] ボタンをクリックします。
