---
title: ビジネス向け Microsoft Defender を取得する
description: ビジネス向け Microsoft Defender を取得する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/11/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security-compliance
ms.openlocfilehash: 7bdce06b14610718e642d06d1f5a99ac09707a5d
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767342"
---
# <a name="get-microsoft-defender-for-business-preview"></a>ビジネス向け Microsoft Defender を取得する (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](mdb-tutorials.md#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) はプレビューで利用できます。 プレビュー プログラムに参加すると、一般に利用可能になる前に Defender for Business を試用できます。 プレビュー プログラムは、次の場合に使用できます。

- 中小企業に IT サービスを提供する Microsoft パートナー
- 中小企業 (最大 300 人の従業員)

## <a name="sign-up-for-the-preview-program"></a>プレビュー プログラムにサインアップする

1. Visit [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview).

2. [顧客 **] または [****Microsoft パートナー] を選択します**。

3. Microsoft Defender for Business Preview Agreement の条項を確認して同意し、[次へ] を選択 **します**。

4. 連絡先情報をフォームに入力します。 

   - Microsoft パートナーを使用している顧客の場合は、[その他] ボックスにパートナーの組織名を入力します。 [ **Submit**] を選びます。
   - Microsoft パートナーの場合は、パートナーの種類と、作業を計画している顧客に関する情報を必ず示してください。

5. フォームへの入力が完了したら、[送信] を選択 **します**。

## <a name="what-to-expect-after-applying"></a>適用後に期待する情報

アプリケーションを確認し、決定します。 その後、プロモーション コードが含まれるか、現時点で試用版プログラムを提供できない理由を説明するメールが届きます。

承認された場合、メールには、Defender for Business 試用版のライセンス認証に使用するライセンス コードが含まれる。

> [!IMPORTANT]
> パートナーである場合は、プレビュー プログラムに同意した後、各顧客に「プレビュー プログラムにサインアップする」セクションで説明されているプロセスを [完了する必要があります](#sign-up-for-the-preview-program)。 顧客が [その他] ボックスに Microsoft パートナー **名を指定** してください。

## <a name="two-portals-for-setup"></a>セットアップ用の 2 つのポータル

試用版を開始する準備ができたら、2 つのメイン ポータルを使用して設定を行います。 次の表に、使用する 2 つのメイン ポータルの概要を示します。 <br/><br/>

|portal  |説明  |
|---------|---------|
| the Microsoft 365 管理センター ([https://admin.microsoft.com/](https://admin.microsoft.com/))      | ユーザーの追加Microsoft 365 管理センター削除、ユーザー ライセンスの割り当て、製品とサービスの表示、およびサブスクリプションのセットアップ タスクのMicrosoft 365します。 <br/><br/> 詳細については、「概要」[を参照Microsoft 365 管理センター](../../admin/admin-overview/admin-center-overview.md)。      |
| ポータルMicrosoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com))     | 電子メール保護Microsoft 365 Defender組織のデバイスのセキュリティ設定を管理するには、Microsoft 365 Defender ポータルを使用します。 <br/><br/>詳細については、「ポータルの使用を開始する[」をMicrosoft 365 Defenderしてください](mdb-get-started.md)。        |

組織がデバイスの管理に Microsoft Intune (Microsoft エンドポイント マネージャー の一部) を使用している場合は、管理センター ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) Microsoft エンドポイント マネージャーを使用することもできます。 詳細については、「デバイスMicrosoft Intune [MDM および MAM プロバイダーである」を参照してください](/mem/intune/fundamentals/what-is-intune)。

## <a name="view-and-manage-users"></a>ユーザーの表示と管理

1. [サブスクリプション] Microsoft 365 管理センターに移動[https://admin.microsoft.com/](https://admin.microsoft.com/)し、試用版サブスクリプションの要求に使用したアカウントと同じアカウントを使用してサインインします。

2. ナビゲーション ウィンドウで、[**UsersActive** >  users] **を選択します**。 ユーザーの一覧を確認します。 

3. ユーザーを追加するには、「ユーザーの追加とライセンスの同時割り当て」の [ガイダンスに従います](../../admin/add-users/add-users.md)。

これで、Microsoft Defender for Business (プレビュー) の設定と構成 [に進む準備ができました](mdb-setup-configuration.md)。


## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business のセットアップと構成プロセス (プレビュー) を参照してください。](mdb-setup-configuration.md)

- [ウィザードを使用して Microsoft Defender for Business をセットアップする (プレビュー)](mdb-use-wizard.md)

- [Microsoft Defender for Business のヘルプとサポートを受ける方法 (プレビュー)](mdb-get-help.md)