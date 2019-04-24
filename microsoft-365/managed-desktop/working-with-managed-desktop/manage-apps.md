---
title: Microsoft マネージドデスクトップでのアプリの管理
description: Microsoft マネージドデスクトップデバイスに展開されている基幹業務アプリを更新する方法に関する情報
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ce2765ef2ab176dc5d9a1d41db7e26549b007d79
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285947"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップで基幹業務アプリを管理する

<!--Application management -->

microsoft マネージドデスクトップに利用したアプリのアプリの更新を管理するには、いくつかの方法があります。また、microsoft マネージドデスクトップデバイスに展開されています。 Microsoft 管理デスクトップポータルまたは Intune でアプリの更新を行うことができます。 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップで基幹業務アプリを更新する

**Microsoft マネージドデスクトップポータルで基幹業務アプリを更新するには**
1. [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mmdportal)にサインインします。
2. [**インベントリ**] で、[**アプリ**] を選択します。  
3. 更新するアプリを選択し、[**編集**] を選択します。
4. [**管理**] で、[**プロパティ**] を選択します。 
5. [**アプリパッケージファイル**] をクリックし、新しいアプリパッケージファイルを参照してアップロードします。
6. [**アプリパッケージファイル**] を選択します。
7. フォルダーアイコンを選択し、更新されたアプリファイルの場所を参照します。 [**開く**] を選択します。 アプリ情報がパッケージ情報で更新されます。
8. アプリの**バージョン**が更新されたアプリパッケージを反映していることを確認します。 

更新したアプリは、ユーザーのデバイスに展開されます。

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Intune で基幹業務アプリを更新する

**Intune で基幹業務アプリを更新するには**
1. [Azure portal](https://azure.portal.com)にサインインします。
2. [**すべてのサービス** > ]**Intune**を選択します。 Intune は、[**監視 + 管理**] セクションにあります。
3. [**クライアントアプリ > アプリ**] を選択します。
4. アプリの一覧でアプリを見つけて選択します。
5. **概要**ブレードで、[**プロパティ**] を選択します。
6. [**アプリパッケージファイル**] を選択します。
7. フォルダーアイコンを選択し、更新されたアプリファイルの場所を参照します。 [**開く**] を選択します。 アプリ情報がパッケージ情報で更新されます。
8. アプリの**バージョン**が更新されたアプリパッケージを反映していることを確認します。

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>アプリを以前のバージョンにロールバックする

新しいバージョンのアプリを展開したときにエラーが検出された場合は、以前のバージョンにロールバックできます。 ここで説明するプロセスは、種類が**windows MSI 基幹業務アプリ**または windows アプリとしてリストされているアプリ **(Win 32) です。**

**基幹業務アプリを以前のバージョンにロールバックするには**

1. [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mmdportal)にサインインします。
2. [**インベントリ**] で、[**アプリ**] を選択します。  
3. ロールバックする必要のあるアプリを選択し、[**編集**] を選択します。
4. [**管理**] で、[**プロパティ**] を選択します。 
    - **Windows MSI 基幹業務アプリ**アプリの場合は、[**アプリ情報**] を選択し、[**アプリのバージョンを無視**する] で [**はい**] を選択します。
    - **Windows アプリの場合 (Win 32)-** アプリのプレビューを表示するには、[**アプリ情報**] を選択し、[**検出ルール**] を選択してから [**追加**] を選択します。 
    msi ルールがある場合は、[ **msi 製品バージョン] チェック**が [**いいえ**] に設定されていることを確認します。
5. [以前のバージョンのアプリソースファイル](../get-started/deploy-apps.md)を Microsoft Managed Desktop 管理ポータルにアップロードします。  

