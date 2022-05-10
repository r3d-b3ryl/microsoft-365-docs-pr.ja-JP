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
ms.openlocfilehash: 1dabe2d16dc2d559ec1576a2140c48b63c8e2ccd
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2022
ms.locfileid: "65285626"
---
# <a name="allow-cookies-for-lms-urls-in-your-browser"></a>ブラウザーで LMS URL の Cookie を許可する

IMS Global 標準に従って LTI 1.3 ハンドシェイクを完了するには、サード パーティのブラウザー Cookie が必要です。 したがって、ラーニング管理システム (LMS) から LTI ツールを起動する場合、ブラウザー設定で LMS URL のサード パーティの Cookie を許可する必要があります。

ブラウザーで Cookie を許可する手順を次に示します。

# <a name="microsoft-edge"></a>[Microsoft Edge](#tab/edge)

## <a name="allow-cookies-for-lms-urls-in-microsoft-edge"></a>Microsoft Edgeで LMS URL の Cookie を許可する

1. Edge **設定** window で、 **Cookies と site permissionsCookies** >  **と data storedManage** > を選択 **し、Cookie とサイト データを削除** します。
2. Cookie  **データを保存して読み取るにはAllow サイトを有効にしてください (推奨)**、 **Block サード パーティの Cookiesis**  がオフになっていることを確認します。

サード パーティの Cookie をブロックしたままにする必要がある場合:

1. Edge **設定** window で、 **Cookies と site permissionsCookies** >  **と data storedManage** > を選択 **し、Cookie とサイト データを削除** します。
2.  **UnderAllow** で、LMS プラットフォームのドメイン URL を追加する場合は、 **Addto**  を選択します。
   1. たとえば、LMS プラットフォームがホストされている `https://contoso.com`場合は、その URL を **[許可**] に追加する必要があります。

![Microsoft Edge Cookie 設定ページのスクリーンショット](media/edge-cookies.png)

# <a name="google-chrome"></a>[Google Chrome](#tab/chrome)

## <a name="allow-cookies-for-lms-urls-in-google-chrome"></a>Google Chrome で LMS URL の Cookie を許可する

1. Chrome **設定** window の **Privacy と securitytab**  で、 **Cookies とその他のサイト データ** を選択します。

2.  **常に Cookie を使用できる UnderSites**、 **selectAdd**、および **このサイト** チェック ボックスでサード パーティの Cookie を含むを選択します。

3. LMS プラットフォームのドメイン URL を追加します。
   1. たとえば、LMS プラットフォームがホストされている `https://contoso.com`場合は、その URL を使用する必要があります。

![Google Chrome Cookie 設定ページのスクリーンショット](media/chrome-cookies.png)

# <a name="mozilla-firefox"></a>[Mozilla Firefox](#tab/firefox)

## <a name="allow-cookies-for-lms-urls-in-mozilla-firefox"></a>Mozilla Firefox で LMS URL の Cookie を許可する

1. Firefox **設定** window で、[ **Privacy & Security** ] タブを選択します。

2. [ **UnderCookies] と [サイト データ**] の [ **Manage 例外]** を選択します。

3. [Web サイト  **テキストのアドレス**] ボックスに、LMS プラットフォームの URL を入力します。
   1. たとえば、LMS プラットフォームがホストされている `https://contoso.com`場合は、その URL を使用する必要があります。

4. [ **許可] を** 選択して、入力した Web サイトの Cookie を許可します。

5. 変更 **の保存** を選択します。

![Mozilla Firefox Cookie 設定ページのスクリーンショット](media/firefox-cookies.png)

# <a name="safari"></a>[Safari](#tab/safari)

## <a name="allow-cookies-for-lms-urls-in-safari"></a>Safari で LMS URL の Cookie を許可する

1.  **SelectPreferencesPrivacy** >. ****

2. [ **Prevent クロスサイト追跡** ]チェック ボックスをオフにしてください。

---

> [!NOTE]
> 自分で設定を変更することはできません (ブラウザーは組織によって管理されています)、IT 部門に問い合わせてください。
