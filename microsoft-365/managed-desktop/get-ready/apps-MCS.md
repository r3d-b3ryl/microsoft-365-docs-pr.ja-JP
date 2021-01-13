---
title: Microsoft コンサルティング サービスを使用する
description: MCS を使用してアプリをパッケージ化するための準備と手順
keywords: Microsoft マネージド デスクトップ, Microsoft 365, サービス, ドキュメント, アプリ, MCS, パッケージ化
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841425"
---
# <a name="working-with-microsoft-consulting-services"></a>Microsoft コンサルティング サービスを使用する

Microsoft Consulting Services (MCS) と関わり、Microsoft マネージド デスクトップで使用するためにアプリをパッケージ化できます。 詳細については、アカウント担当者と連絡を取り、MCS に連絡し、特定のアプリ パッケージ プロジェクトの範囲を設定します。

## <a name="roles-and-responsibilities"></a>役割と責任

MCS アプリパッケージを使用するには、次 **の要素を指定する必要があります**。

- ソース インストーラー ファイル (たとえば、setup.exe .msi)。
- インストール手順。最終的なインストールの外観に関する詳細を指定します。 たとえば、アプリへのデスクトップ ショートカットが必要ですか? アプリの可視性を確認する必要がありますか。 アプリはサーバーに接続する必要があります。接続されている場合は、どちらですか。 詳細については、アプリケーション パッケージ [要求テンプレートを参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。
- 独自の受け入れテストを実行して、アプリが環境内で必要な動作を確認する必要があります。

**MCS は、次の処理を行います。**

- Microsoft マネージド デスクトップ環境でアプリが禁止または制限されているかどうかを確認します。
- Windows 10 との互換性を確保するためのアプリのインストール、開始、アンインストールのテスト。 MCS が互換性の問題を検出すると、修復のために Desktop App [Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) プログラムにアプリを渡します。
- アプリを仕様にパッケージ化し、Microsoft Intune を使用してアプリの展開をテストします。

## <a name="app-delivery-schedule"></a>アプリの配信スケジュール

アプリ情報を Microsoft マネージド デスクトップ ポータルにアップロードして、パッケージ化プロセスを開始します。 パッケージ チームは、毎週木曜日に新しい提出をレビューします。 レビューとパッケージ化の後、パッケージ アプリは次の金曜日に配信されます。 1 週間に最大 5 つのアプリをパッケージ化して開始できますが、サービスはニーズに合わせて拡大できます。

![木曜日 (この例では 21 日)、翌日のメディア検証、次の月曜日 (25 日) のパッケージ化、後続の金曜日 (29 日) のアプリ配信を示すカレンダー](../../media/MCS-cal.png)

アプリが配信された後に通知されます。 その時点で、Microsoft マネージド デスクトップ ポータルで承認テストを実行し、作業を承認するには 21 日間があります。 受け入れテスト中にアプリに関する問題を発見した場合は、Microsoft マネージド デスクトップ ポータルでアプリを拒否すると、MCS パッケージーとメールで接続し、問題を理解して解決します。

## <a name="testing-accounts-and-environment"></a>アカウントと環境のテスト

パッケージ チームが Microsoft Intune への移行を完了するには、特定のアクセス許可を提供することをお勧めします。
 
-   アプリを追加して割り当てるパッケージ化者向け Microsoft Intune のアプリ展開機能へのアクセス 
-   アプリをテストできるパッケージのグループ、ユーザー アカウント、ライセンスをテストする

MCS は、これらのアクセス許可を使用して次のアクションを実行します。
 
-   Microsoft マネージド デスクトップ用に構成された仮想マシンでアプリが動作するようにする
-   ユーザーへの展開のためにアプリを Microsoft Intune にアップロードする

これらのアクセス許可がない場合、MCS は先に進む可能性がありますが、アプリケーションを環境にアップロードすることはできません。


