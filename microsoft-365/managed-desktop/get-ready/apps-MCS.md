---
title: Microsoft コンサルティング サービスを使用する
description: MCS を使用してアプリをパッケージ化するための準備と手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: db48122ea5551fe3e9f8cd676785bbd3eef81d0b
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58570931"
---
# <a name="working-with-microsoft-consulting-services"></a>Microsoft コンサルティング サービスを使用する

Microsoft Consulting Services (MCS) に参加して、アプリをパッケージ化して、ユーザーと一緒に使用Microsoft マネージド デスクトップ。 詳細については、アカウント担当者と一緒に MCS に問い合わせ、特定のアプリ パッケージ プロジェクトの範囲を指定します。

## <a name="roles-and-responsibilities"></a>役割と責任

MCS アプリパッケージを使用するには、 **次の要素を指定する必要があります**。

- ソース インストーラー ファイル (たとえば、setup.exeまたは.msi)。
- 最終的なインストールの外観に関する詳細を指定するインストール手順。 たとえば、アプリへのデスクトップ ショートカットがある必要がありますか? アプリの表示設定は何ですか? アプリがサーバーに接続する必要があります。その場合、どちらに接続しますか? 詳細については、「アプリケーション パッケージ [要求テンプレート」を参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。
- 独自の受け入れテストを実行して、環境内で必要に応じてアプリが動作する方法を確認する必要があります。

**MCS は、次のアクションを処理します。**

- アプリが環境内で禁止または制限されているかどうかをMicrosoft マネージド デスクトップします。
- アプリのインストール、開始、アンインストールをテストして、アプリとの互換性をWindows 10。 MCS で互換性の問題が検出された場合、アプリは修復のために [App Assure](/fasttrack/products-and-capabilities#app-assure) プログラムに渡されます。
- アプリを仕様にパッケージ化し、アプリの展開をテストするには、アプリを使用Microsoft Intune。

## <a name="app-delivery-schedule"></a>アプリの配信スケジュール

アプリ情報をポータルにアップロードして、パッケージ化プロセスMicrosoft マネージド デスクトップします。 パッケージ チームは、毎週木曜日に新しい申請を確認します。 確認とパッケージ化の後、パッケージ化されたアプリは次の金曜日に配信されます。 週に最大 5 つのアプリをパッケージ化して開始できますが、サービスはニーズに合わせて拡張できます。

![木曜日 (この例では 21 日) のアプリの流入、次の日のメディア検証、次の月曜日 (25 日) のパッケージ化、および後続の金曜日 (29 日) のアプリ配信を示すカレンダー。](../../media/MCS-cal.png)

アプリが配信された後に通知されます。 この時点で、受け入れテストを実行し、ポータルで作業を承認するには 21 Microsoft マネージド デスクトップがあります。 受け入れテスト中にアプリに関する問題を発見した場合は、Microsoft マネージド デスクトップ ポータルでアプリを拒否し、問題を理解して解決するために MCS パッケージーと電子メールで接続されます。

## <a name="testing-accounts-and-environment"></a>アカウントと環境のテスト

パッケージ チームがパッケージ への移行を完了Microsoft Intune、特定のアクセス許可を提供することをお勧めします。

- パッケージMicrosoft Intuneアプリを追加および割り当てるアプリの展開機能へのアクセス
- パッケージ作成者がアプリをテストできるテスト グループ、ユーザー アカウント、ライセンス

MCS は、これらのアクセス許可を使用して次のアクションを実行します。

- アプリが仮想マシン用に構成された仮想マシンで動作Microsoft マネージド デスクトップ
- ユーザーに展開Microsoft Intuneアプリをアップロードする

これらのアクセス許可がない場合、MCS は前進できますが、アプリケーションを環境にアップロードすることはできません。
