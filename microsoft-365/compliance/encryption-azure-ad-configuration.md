---
title: Microsoft Purview 情報保護によって暗号化されたコンテンツの Azure AD 構成
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection: M365-security-compliance
description: Microsoft Purview 情報保護によって暗号化されたコンテンツの Azure AD クロステナント アクセス設定と条件付きアクセス ポリシーを構成する方法。
ms.openlocfilehash: 0a99dc12c8ff779008add2f37cdbe4ed7e1f263a
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384582"
---
# <a name="azure-ad-configuration-for-encrypted-content"></a>暗号化されたコンテンツの Azure AD 構成

Microsoft Purview 情報保護[から Azure](information-protection.md) Rights Management Service からの暗号化を使用して電子メールやドキュメントなどの機密アイテムを保護する場合、この暗号化されたコンテンツへの承認されたアクセスを妨げる Azure Active Directory (Azure AD) 構成がいくつかあります。

同様に、ユーザーが別の組織から暗号化されたメールを受け取ったり、Azure Rights Management Service を使用してドキュメントを暗号化する他の組織と共同作業したりする場合、ユーザーは自分の Azure AD の構成方法のために、そのメールやドキュメントを開けることができない可能性があります。

例:

- ユーザーは、別の組織から送信された暗号化された電子メールを開くできません。 または、別の組織の受信者が、送信した暗号化された電子メールを開けないことをユーザーが報告します。

- 組織は共同プロジェクトで別の組織と共同作業を行い、プロジェクト ドキュメントは暗号化され、Azure AD のグループを使用してアクセスを許可することで保護されます。 ユーザーは、他の組織のユーザーによって暗号化されたドキュメントを開くできません。

- ユーザーは、オフィスにいるときに暗号化されたドキュメントを正常に開くことができますが、リモートでこのドキュメントにアクセスしようとすると、多要素認証 (MFA) を求められる場合は開けられません。

暗号化サービスへのアクセスが誤ってブロックされないようにするには、次のセクションを使用して組織の Azure AD を構成するか、別の組織の Azure AD 管理者に情報を中継します。 このサービスにアクセスしないと、ユーザーは認証され、暗号化されたコンテンツを開く権限を与えられません。

## <a name="cross-tenant-access-settings-and-encrypted-content"></a>クロステナント アクセス設定と暗号化されたコンテンツ

> [!IMPORTANT]
> 別の組織のテナント間アクセス設定は、ユーザーが暗号化したコンテンツを開くことができないか、ユーザーが他の組織によって暗号化されたコンテンツを開くことができないかのどちらかを担当できます。
> 
> ユーザーに表示されるメッセージは、アクセスをブロックした組織を示します。 別の組織からこのセクションに Azure AD 管理者を誘導することが必要になる場合があります。

既定では、ユーザーが Azure Rights Management Service からの暗号化を使用してコンテンツを保護するときに、クロステナント認証が機能するように構成する必要はありません。 ただし、組織では、Azure AD [外部 ID クロステナント アクセス設定](/azure/active-directory/external-identities/cross-tenant-access-overview)を使用してアクセスを制限できます。 逆に、別の組織でこれらの設定を構成して、組織内のユーザーとのアクセスを制限することもできます。 これらの設定は、暗号化されたメールや暗号化されたドキュメントを含む、暗号化されたアイテムを開くことに影響します。

たとえば、別の組織では、ユーザーが組織によって暗号化されたコンテンツを開くことができない設定が構成されている場合があります。 このシナリオでは、Azure AD 管理者がクロステナント設定を再構成するまで、そのコンテンツを開こうとする外部ユーザーに、テナント **管理者** への参照 **を使用して組織によってアクセスがブロックされていることを** 知らせるメッセージが表示されます。

Fabrikam, Inc 組織からサインインしているユーザーのローカル Azure AD がアクセスをブロックした場合のメッセージの例を次に示します。

![ローカル Azure AD テナントが暗号化されたコンテンツへのアクセスをブロックする場合のメッセージの例。](../media/blocked-by-your-org.png)

アクセスをブロックする Azure AD 構成の場合、ユーザーにも同様のメッセージが表示されます。

サインインしているユーザーの観点から見ると、アクセスのブロックを担当する別の Azure AD 組織である場合、メッセージ **は組織によって Access** に変更され、メッセージの本文にその他の組織のドメイン名が表示されます。 例:

![別の Azure AD テナントが暗号化されたコンテンツへのアクセスをブロックする場合のメッセージの例。](../media/blocked-by-external-org.png)

テナント間アクセス設定がアプリケーションによるアクセスを制限する場合は常に、アプリケーション ID が次の **Microsoft Azure Information Protection** へのアクセスを許可するように構成する必要があります。

````plaintext
00000012-0000-0000-c000-000000000000
````

このアクセスが許可されていない場合、ユーザーは認証され、暗号化されたコンテンツを開くことを承認することはできません。 この構成は、既定の設定と組織の設定として設定できます。

- 別の組織との暗号化されたコンテンツの共有を許可するには、Microsoft Azure Information Protection (ID: 00000012-0000-0000-c000-0000-00000000000) へのアクセスを許可する受信設定を作成します。 

- ユーザーが他の組織から受信する暗号化されたコンテンツへのアクセスを許可するには、Microsoft Azure Information Protectionへのアクセスを許可する送信設定を作成します (ID: 00000012-0000-0000-c000-0000000000)

これらの設定が Microsoft Azure Information Protection用に構成されると、アプリケーションに **Microsoft Rights Management Services** が表示されます。

これらのテナント間アクセス設定を構成する手順については、「 [B2B コラボレーションのテナント間アクセス設定を構成する」を](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-collaboration)参照してください。

ユーザーに対して多要素認証 (MFA) を必要とする Azure AD 条件付きアクセス ポリシーも構成している場合は、暗号化されたコンテンツに条件付きアクセスを構成する方法について次のセクションを参照してください。

## <a name="conditional-access-policies-and-encrypted-documents"></a>条件付きアクセス ポリシーと暗号化されたドキュメント

組織が **Microsoft Azure Information Protection** を含む [Azure Active Directory 条件付きアクセス ポリシー](/azure/active-directory/conditional-access/overview)を実装しており、そのポリシーが組織によって暗号化されたドキュメントを開く必要がある外部ユーザーに適用される場合:

- 独自のテナントに Azure AD アカウントを持つ外部ユーザーの場合は、 [外部 ID クロステナント アクセス設定](/azure/active-directory/external-identities/cross-tenant-access-overview) を使用して、1 つ、多くの、またはすべての外部 Azure AD 組織からの MFA 要求の信頼設定を構成することをお勧めします。

- 前のエントリでカバーされていない外部ユーザー (Azure AD アカウントを持っていないユーザーや、信頼設定のテナント間アクセス設定を構成していないユーザーなど) の場合、これらの外部ユーザーはテナントにゲスト アカウントを持っている必要があります。
    
これらの構成のいずれかを行わないと、外部ユーザーは暗号化されたコンテンツを開くことができず、エラー メッセージが表示されます。 メッセージ テキストは、アカウントをテナントの外部ユーザーとして追加する必要があることを通知する場合があります。このシナリオでは、「**別の Azure Active Directory ユーザー アカウントでサインアウトして再度サインインする**」という誤った指示があります。

組織によって暗号化されたコンテンツを開く必要がある外部ユーザーに対してこれらの構成要件を満たしていない場合は、条件付きアクセス ポリシーから Microsoft Azure Information Protectionを削除するか、ポリシーから外部ユーザーを除外する必要があります。

詳細については、よく寄せられる質問を参照してください。[Azure Information Protectionが条件付きアクセスに使用可能なクラウド アプリとして一覧表示されています。この動作のしくみは?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="guest-accounts-for-external-users-to-open-encrypted-documents"></a>外部ユーザーが暗号化されたドキュメントを開くゲスト アカウント

外部ユーザーが組織によって暗号化されたドキュメントを開くには、Azure AD テナント内のゲスト アカウントが必要になる場合があります。 ゲスト アカウントを作成するオプション:

- これらのゲスト アカウントを自分で作成します。 これらのユーザーがすでに使用している任意のメール アドレスを指定できます。 たとえば、Gmail アドレスです。
    
    このオプションの利点は、暗号化設定でメール アドレスを指定することにより、特定のユーザーへのアクセスと権利を制限できることです。 欠点は、アカウントの作成とラベル構成の調整のための管理オーバーヘッドです。

- [SharePoint と OneDrive と Azure AD B2B の統合](/sharepoint/sharepoint-azureb2b-integration)を使用すると、ユーザーがリンクを共有するときにゲスト アカウントが自動的に作成されます。
    
    このオプションの利点は、アカウントが自動的に作成されるため、管理オーバーヘッドが最小限に抑えられ、ラベルの構成が簡単になることです。 このシナリオでは、事前にメール アドレスがわからないため、暗号化オプション [[認証されたユーザーを追加する]](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) を選択する必要があります。 欠点は、この設定ではアクセス権と使用権を特定のユーザーに制限できないことです。

外部ユーザーは、Windows および Microsoft 365 Apps ([以前の Office 365 アプリ](/deployoffice/name-change)) または Office 2019 のスタンドアロン エディションを使用するときに、Microsoft アカウントを使用して暗号化されたドキュメントを開くこともできます。 最近では他のプラットフォームでもサポートされており、macOS (Microsoft 365 Apps、バージョン 16.42 以降)、Android (バージョン 16.0.13029 以降)、iOS (バージョン 2.42 以降) で暗号化されたドキュメントを開くためにも Microsoft アカウントがサポートされています。 

たとえば、組織内のユーザーが暗号化されたドキュメントを組織外のユーザーと共有し、暗号化設定で外部ユーザーの Gmail メール アドレスを指定します。 この外部ユーザーは、Gmail メール アドレスを使用する独自の Microsoft アカウントを作成できます。 次に、このアカウントでサインインした後、指定された使用制限に従って、ドキュメントを開いて編集できます。 このシナリオのチュートリアルの例については、「[保護されたドキュメントを開いて編集する](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)」を参照してください。

> [!NOTE]
> Microsoft アカウントのメール アドレスは、暗号化設定へのアクセスを制限するために指定されたメール アドレスと一致する必要があります。

Microsoft アカウントを持つユーザーがこの方法で暗号化されたドキュメントを開くと、同じ名前のゲスト アカウントがまだ存在しない場合、テナントのゲスト アカウントが自動的に作成されます。 ゲスト アカウントが存在する場合は、サポートされているデスクトップおよびモバイル Office アプリから暗号化されたドキュメントを開くだけでなく、Office on the web を使用して SharePoint および OneDrive でドキュメントを開くために使用できます。

ただし、このシナリオでは、レプリケーションの待ち時間のため、自動ゲスト アカウントはすぐには作成されません。 暗号化設定の一部として個人用電子メール アドレスを指定する場合は、Azure Active Directory に対応するゲスト アカウントを作成することをお勧めします。 次に、これらのユーザーに、組織から暗号化されたドキュメントを開くにはこのアカウントを使用する必要があることを知らせます。

> [!TIP]
> 外部ユーザーがサポートされている Office クライアント アプリを使用するかどうかを確認できないため、ゲスト アカウントを作成した後 (特定のユーザーの場合)、または [SharePoint および OneDrive の Azure AD B2B との統合](/sharepoint/sharepoint-azureb2b-integration-preview)を使用するとき (認証されたユーザーの場合) は、SharePoint と OneDrive からのリンクを共有する方が外部ユーザーとの安全なコラボレーションをサポートするためのより信頼性の高い方法です。

## <a name="next-steps"></a>次の手順

[機密ラベル](sensitivity-labels.md)を使用してドキュメントと電子メールを暗号化する場合は、[外部ユーザーのサポートとラベル付きコンテンツ](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)に関心を持ち、テナント間で適用されるラベル設定を理解することができます。 

暗号化サービスにアクセスする方法とタイミングについては、「 [Azure RMS のしくみのチュートリアル:初回使用、コンテンツ保護、コンテンツの使用](/azure/information-protection/how-does-it-work#walkthrough-of-how-azure-rms-works-first-use-content-protection-content-consumption)」を参照してください。


