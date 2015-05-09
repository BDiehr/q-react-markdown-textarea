q-react-markdown-textarea
=======================

This is a fork that is very similar to the one Kyle Mathews developed. I highly recommend looking at his documentation : http://kyleamathews.github.io/react-markdown-textarea/

**So what's the difference?**

I added in the property clearOnSave. There are two things you need to know:

- clearOnSave defaults to false
- The text only gets cleared if clearOnSave is true, **and** your save method returns true. This will allow you to take into account
any validation you would like to do before saving.

Sample implementation:


    import MarkdownTextarea from 'q-react-markdown-textarea';
    
    constructor() {
        this.state = {
            title: ''
        };
    }

    // This will be the method passed down into the q-react-markdown-textarea
    onSave(text) {
        // Any function that returns a boolean
        let isValidState = this.state.title != ''; 
        
        if(isValidState) {
            this.save(text);
        }

        return isValidPost;
    }
    
    render() {
        return (
            <MarkdownTextarea
                clearOnSave={true}
                initialValue={this.props.text}
                onSave={this.onSave.bind(this)}
                />
        );
    }

And that's all!