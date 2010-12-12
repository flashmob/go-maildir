# PACKAGE

package maildir

This package is used for writing mails to a maildir, according to
the specification located at http://www.courier-mta.org/maildir.html


# TYPES

	type Maildir struct {
		// contains unexported fields
	}
Represent a folder in a maildir. The root folder is usually the Inbox.

`func New(path string, create bool) (m *Maildir, err os.Error)`

Open a maildir. If create is true and the maildir does not exist, create it.

`func (m *Maildir) Child(name string, create bool) (*Maildir, os.Error)`

Get a subfolder of the current folder. If create is true and the folder does not
exist, create it.

`func (m *Maildir) CreateMail(data io.Reader) (filename string, err os.Error)`

Write a mail to the maildir folder. The data is not encoded or compressed in any way.
