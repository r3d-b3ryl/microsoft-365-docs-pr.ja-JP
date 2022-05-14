---
title: ブラウザーで LMS URL の Cookie を許可する
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Edge、Chrome、Firefox、Safari ブラウザーで LMS URL の Cookie を許可する方法について説明します。
ms.openlocfilehash: 84ba252f9d3854fad4e89bd6e9dac8d0b020cf3a
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65414784"
---
# <a name="allow-cookies-for-lms-urls-in-your-browser"></a>ブラウザーで LMS URL の Cookie を許可する

IMS Global 標準に従って LTI 1.3 ハンドシェイクを完了するには、サード パーティのブラウザー Cookie が必要です。 したがって、ラーニング管理システム (LMS) から LTI ツールを起動する場合、ブラウザー設定で LMS URL のサード パーティの Cookie を許可する必要があります。

ブラウザーで Cookie を許可する手順を次に示します。

# <a name="microsoft-edge"></a>[Microsoft Edge](#tab/edge)

## <a name="allow-cookies-for-lms-urls-in-microsoft-edge"></a>Microsoft Edgeで LMS URL の Cookie を許可する

1. Edge の [**設定**] ウィンドウで、[**Cookie とサイトのアクセス許可** > ]、[**保存された Cookie とデータ** > ]、[**Cookie とサイト データの管理と削除**] を選択します。
2. [**サイトに Cookie データの保存と読み取りを許可する (推奨)**] をオンにし、[**サード パーティの Cookie をブロックする**] がオフになっていることを確認します。

サード パーティの Cookie をブロックしたままにする必要がある場合:

1. Edge の [**設定**] ウィンドウで、[**Cookie とサイトのアクセス許可** > ]、[**保存された Cookie とデータ** > ]、[**Cookie とサイト データの管理と削除**] を選択します。
2. [ **許可]** で [ **追加]** を選択し、LMS プラットフォームのドメイン URL を追加します。
   1. たとえば、LMS プラットフォームがホストされている `https://contoso.com`場合は、その URL を **[許可**] に追加する必要があります。

![Microsoft Edge Cookie 設定ページのスクリーンショット](media/edge-cookies.png)

# <a name="google-chrome"></a>[Google Chrome](#tab/chrome)

## <a name="allow-cookies-for-lms-urls-in-google-chrome"></a>Google Chrome で LMS URL の Cookie を許可する

1. Chrome の [**設定**] ウィンドウの [**プライバシーとセキュリティ**] タブで、[**Cookie と他のサイト データ**] を選択します。

2. [**常に Cookie を使用できるサイト**] で、[**追加**] を選択し、[**このサイトでサードパーティの Cookie を許可する**] チェック ボックスを選択します。

3. LMS プラットフォームのドメイン URL を追加します。
   1. たとえば、LMS プラットフォームがホストされている `https://contoso.com`場合は、その URL を使用する必要があります。

![Google Chrome Cookie 設定ページのスクリーンショット](media/chrome-cookies.png)

# <a name="mozilla-firefox"></a>[Mozilla Firefox](#tab/firefox)

## <a name="allow-cookies-for-lms-urls-in-mozilla-firefox"></a>Mozilla Firefox で LMS URL の Cookie を許可する

1. Firefox の [**設定**] ウィンドウで、 [**プライバシーとセキュリティ**] タブを選択します。

2. [**Cookie とサイト データ**] で、 [**例外を管理**] を選択します。

3. [ **Web サイトのアドレス** ] テキスト ボックスに、LMS プラットフォームの URL を入力します。
   1. たとえば、LMS プラットフォームがホストされている `https://contoso.com`場合は、その URL を使用する必要があります。

4. [ **許可] を** 選択して、入力した Web サイトの Cookie を許可します。

5. [**変更を保存**] を選択します。

![Mozilla Firefox Cookie 設定ページのスクリーンショット](media/firefox-cookies.png)

# <a name="safari"></a>[Safari](#tab/safari)

## <a name="allow-cookies-for-lms-urls-in-safari"></a>Safari で LMS URL の Cookie を許可する

1. [**環境設定**] >  [**プライバシー**] の順に選択します。

2. [**サイト越えトラッキングを防ぐ**] チェック ボックスをオフにします。

---

> [!NOTE]
> 自分で設定を変更することはできません (ブラウザーは組織によって管理されています)、IT 部門に問い合わせてください。
