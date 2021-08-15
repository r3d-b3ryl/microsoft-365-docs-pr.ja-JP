---
title: アプリを管理Microsoft マネージド デスクトップ
description: デバイスに展開されている業務用アプリを更新する方法Microsoft マネージド デスクトップ情報
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ffa1d96e1a700049fcfad47f9be15376fa3bd8ee566be08707a2b559e66b8c9d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53904265"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップでの基幹業務アプリの管理

<!--Application management -->

アプリにオンボードし、Microsoft マネージド デスクトップデバイスに展開したアプリのアプリ更新プログラムを管理Microsoft マネージド デスクトップがあります。 アプリの更新は、ポータルMicrosoft マネージド デスクトップ Intune で行います。 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>アプリ内の業務用アプリを更新Microsoft マネージド デスクトップ

**ポータルで業務用アプリを更新するにはMicrosoft マネージド デスクトップ**
1. 管理者ポータルに[サインインMicrosoft マネージド デスクトップします](https://aka.ms/mmdportal)。
2. [インベントリ **] で**、[アプリ] **を選択します**。  
3. 更新するアプリを選択し、[編集] を **選択します**。
4. [管理 **] で**、[プロパティ] **を選択します**。 
5. [ **アプリ パッケージ ファイル] を** クリックし、新しいアプリ パッケージ ファイルをアップロードするために参照します。
6. [アプリ **パッケージ ファイル] を選択します**。
7. フォルダー アイコンを選択し、更新されたアプリ ファイルの場所を参照します。 [**開く**]を選択します。 アプリ情報はパッケージ情報で更新されます。
8. アプリの **バージョンに更新** されたアプリ パッケージが反映されているのを確認します。 

更新されたアプリは、ユーザーのデバイスに展開されます。

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Intune で業務用アプリを更新する

**Intune で業務用アプリを更新するには**
1. Azure portal に [サインインします](https://portal.azure.com)。
2. [すべての **サービス]**  >  **Intune を選択します**。 Intune は [監視と管理 **] セクションに** 表示されます。
3. [クライアント **アプリとアプリ] >選択します**。
4. アプリの一覧でアプリを検索して選択します。
5. [概要] **ブレードで** 、[プロパティ] を **選択します**。
6. [アプリ **パッケージ ファイル] を選択します**。
7. フォルダー アイコンを選択し、更新されたアプリ ファイルの場所を参照します。 [**開く**]を選択します。 アプリ情報はパッケージ情報で更新されます。
8. アプリの **バージョンに更新** されたアプリ パッケージが反映されているのを確認します。

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>アプリを以前のバージョンにロールバックする

新しいバージョンのアプリを展開するときにエラーが見つかった場合は、以前のバージョンにロールバックできます。 ここで説明するプロセスは、MSI Windows **MSI line-of-business** アプリまたは Windows アプリ **(Win 32) - プレビュー** として表示されるアプリ向けです。

**line-of-business アプリを以前のバージョンにロールバックするには**

1. 管理者ポータルに[サインインMicrosoft マネージド デスクトップします](https://aka.ms/mmdportal)。
2. [インベントリ **] で**、[アプリ] **を選択します**。  
3. ロールバックする必要があるアプリを選択し、[編集] を **選択します**。
4. [管理 **] で**、[プロパティ] **を選択します**。 
    - [MSI **Windowsアプリ**] で、[アプリ情報] を選択し、[アプリのバージョンを無視する] で 、[はい] を **選択します**。
    - [Windowsアプリ **(Win 32) -** アプリをプレビューし、[アプリ情報] を選択し、[検出ルール] を選択し、[追加] を **選択します**。 
    MSI ルールがある場合は、MSI **製品の** バージョン チェックが [いいえ] **に設定されています**。
5. [アップロードバージョンのアプリ ソース ファイルを](../get-started/deploy-apps.md)管理ポータルにMicrosoft マネージド デスクトップします。  

