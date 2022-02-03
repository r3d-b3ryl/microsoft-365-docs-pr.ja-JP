---
title: Microsoft Managed Desktop でアプリを管理する
description: Microsoft Managed Desktop デバイスに展開されている業務用アプリを更新する方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: a51be2521924164a8c90a51fcf99328ecf511877
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322556"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップでの基幹業務アプリの管理

<!--Application management -->

アプリの更新プログラムを管理し、Microsoft Managed Desktop デバイスに更新プログラムを展開するには、いくつかの方法があります。 アプリの更新は、Microsoft Managed Desktop ポータルまたは Intune で行います。

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop で業務用アプリを更新する

**Microsoft Managed Desktop ポータルで業務用アプリを更新するには、次の方法を実行します。**

1. [Microsoft Managed Desktop Admin ポータルにサインインします](https://aka.ms/mmdportal)。
1. [インベントリ **] で**、[アプリ] **を選択します**。  
1. 更新するアプリを選択し、[編集] を選択 **します**。
1. [管理 **] で**、[プロパティ] を **選択します**。
1. [ **アプリ パッケージ ファイル] を** 選択し、新しいアプリ パッケージ ファイルをアップロードするために参照します。
1. [アプリ **パッケージ ファイル] を選択します**。
1. フォルダー アイコンを選択し、更新されたアプリ ファイルの場所を参照します。 [**開く**]を選択します。 アプリ情報はパッケージ情報で更新されます。
1. アプリの **バージョンに更新** されたアプリ パッケージが反映されているのを確認します。

更新されたアプリは、ユーザーのデバイスに展開されます。

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Intune で業務用アプリを更新する

**Intune で業務用アプリを更新するには、次の方法を実行します。**

1. Azure portal に [サインインします](https://portal.azure.com)。
2. [**すべてのサービスIntune]** >  **を選択します**。 Intune は [監視と管理 **] セクションに** 表示されます。
3. [ **クライアント アプリとアプリ>選択します**。
4. アプリの一覧でアプリを検索して選択します。
5. [概要] **セクションで** 、[プロパティ] を **選択します**。
6. [アプリ **パッケージ ファイル] を選択します**。
7. フォルダー アイコンを選択し、更新されたアプリ ファイルの場所を参照します。 [**開く**]を選択します。 アプリ情報はパッケージ情報で更新されます。
8. アプリの **バージョンに更新** されたアプリ パッケージが反映されているのを確認します。

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>アプリを以前のバージョンにロールバックする

アプリの新しいバージョンが展開され、エラーが検出された場合は、以前のバージョンにロールバックできます。 以下に説明するプロセスは、**種類が Windows MSI line-of-business** アプリまたは **Windows アプリ (Win 32) - プレビュー** として表示されるアプリ向けです。

**line-of-business アプリを以前のバージョンにロールバックするには、次のコマンドを実行します。**

1. [Microsoft Managed Desktop Admin ポータルにサインインします](https://aka.ms/mmdportal)。
2. [インベントリ **] で**、[アプリ] **を選択します**。  
3. ロールバックする必要があるアプリを選択し、[編集] を選択 **します**。
4. [管理 **] で**、[プロパティ] を **選択します**。
    - [msi **Windowsの** アプリの場合は、[アプリ情報] を選択し、[アプリのバージョンを無視する] で [**はい]** を選択 **します**。
    - [**Windows (Win 32) -** アプリをプレビューし、[アプリ情報] を選択し、[検出ルール] を選択し、[追加] を選択 **します**。
    MSI ルールがある場合は、MSI 製品のバージョン チェックが **[** いいえ] **に設定されています**。
5. [アップロードバージョンのアプリ ソース ファイル](../get-started/deploy-apps.md)を Microsoft Managed Desktop Admin ポータルに追加します。  
