---
title: Microsoft コンサルティング サービスを使用する
description: MCS を使用してアプリをパッケージ化するための準備と手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 9054f77c88ba506a16ce74d364a5a0eea0327793
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035620"
---
# <a name="working-with-microsoft-consulting-services"></a>Microsoft コンサルティング サービスを使用する

Microsoft コンサルティング サービス (MCS) に参加して、Microsoft マネージ デスクトップで使用するためにアプリをパッケージ化できます。 詳細については、アカウント担当者と一緒に MCS に問い合わせ、特定のアプリ パッケージ プロジェクトの範囲を指定します。

## <a name="roles-and-responsibilities"></a>役割と責任

MCS アプリパッケージを使用するには、 **次の要素を指定する必要があります**。

- ソース インストーラー ファイル (たとえば、setup.exeまたは.msi)。
- 最終的なインストールの外観に関する詳細を指定するインストール手順。 たとえば、アプリへのデスクトップ ショートカットがある必要がありますか? アプリの表示設定は何ですか? アプリがサーバーに接続する必要があります。その場合、どちらに接続しますか? 詳細については、「アプリケーション パッケージ [要求テンプレート」を参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。
- 独自の受け入れテストを実行して、環境内で必要に応じてアプリが動作する方法を確認する必要があります。

**MCS は、次のアクションを処理します。**

- Microsoft Managed Desktop 環境でアプリが禁止または制限されているかどうかを確認します。
- アプリのインストール、開始、アンインストールをテストして、アプリとの互換性をWindows 10。 MCS で互換性の問題が検出された場合、アプリは修復のために [App Assure](/fasttrack/products-and-capabilities#app-assure) プログラムに渡されます。
- アプリを仕様にパッケージ化し、アプリの展開をテストするには、アプリを使用Microsoft Intune。

## <a name="app-delivery-schedule"></a>アプリの配信スケジュール

アプリ情報を Microsoft Managed Desktop ポータルにアップロードして、パッケージ化プロセスを開始します。 パッケージ チームは、毎週木曜日に新しい申請を確認します。 確認とパッケージ化の後、パッケージ化されたアプリは次の金曜日に配信されます。 週に最大 5 つのアプリをパッケージ化して開始できますが、サービスはニーズに合わせて拡張できます。

![木曜日 (この例では 21 日) のアプリの流入、次の日のメディア検証、次の月曜日 (25 日) のパッケージ化、および後続の金曜日 (29 日) のアプリ配信を示すカレンダー。](../../media/MCS-cal.png)

アプリが配信された後に通知されます。 その時点で、受け入れテストを実行し、Microsoft Managed Desktop ポータルで作業を承認するには 21 日間が必要です。 受け入れテスト中にアプリに関する問題を発見した場合は、Microsoft Managed Desktop ポータルでアプリを拒否し、問題を理解して解決するために MCS パッケージーに電子メールで接続されます。

## <a name="testing-accounts-and-environment"></a>アカウントと環境のテスト

パッケージ チームがパッケージ への移行を完了Microsoft Intune、特定のアクセス許可を提供することをお勧めします。

- パッケージMicrosoft Intuneアプリを追加および割り当てるアプリの展開機能へのアクセス
- パッケージ作成者がアプリをテストできるテスト グループ、ユーザー アカウント、ライセンス

MCS は、これらのアクセス許可を使用して次のアクションを実行します。

- Microsoft Managed Desktop 用に構成された仮想マシンでアプリが動作するようにする
- ユーザーに展開Microsoft Intuneアプリをアップロードする

これらのアクセス許可がない場合、MCS は前進できますが、アプリケーションを環境にアップロードすることはできません。
